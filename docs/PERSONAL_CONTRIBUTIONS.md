# 개인 개발 기록

Go KarT 팀 공동 프로젝트에서 정광근이 작성한 원본 커밋의 날짜·메시지·실제 코드 변경을 정리했습니다.

**대상:** [원본 팀 저장소](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project)의 `master` · GitHub `author=fourevere` 필터 · 2023-06-13 ~ 2023-06-29

**기록:** 일반 커밋 40개 + 병합 커밋 14개 = 54개. 병합은 협업 기록으로 구분하고, 병합된 팀원 코드를 개인 구현으로 계산하지 않았습니다.

[전체 커밋 목록](COMMIT_HISTORY.md) · [CSV 다운로드](COMMIT_HISTORY.csv)

## 대표 작업

| 작업 | 날짜 | 원본 커밋 |
| --- | --- | --- |
| 게시판 목록·CRUD 구현 | 2023-06-13 | [`9504eb5`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/9504eb5d65938a680eefd3c58d865991bb0a9da3) |
| 게시글 작성자 확인 추가 | 2023-06-14 | [`b2d4ce3`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/b2d4ce30af98edd19dd5cab1de839de4f3d7ce61) |
| 영수증·주문 모델 연결 | 2023-06-26 | [`e804f8b`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/e804f8bbe2f47302fb75a6d968387124d206f62f) |
| 상품 인식 요청의 로그인 확인 | 2023-06-27 | [`2ddf688`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/2ddf688226ea55603f06f5ab79e19891266a340b) |
| 구매 내역 정렬·페이지네이션 | 2023-06-28 | [`5f2ef87`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/5f2ef871b76c40dbb59f22f0dda5f3dcd5182f10) |
| QR 이미지 생성·결과 화면 연동 | 2023-06-28 | [`1d72bdd`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/1d72bdd64cb5e233aeda29331ffd969761fc2264) |

## 실제 코드 변경

아래 diff는 원본 커밋에서 발췌했습니다. `+`는 추가, `-`는 삭제, 앞에 공백이 있는 줄은 주변 문맥입니다. 문맥에 포함된 기존 코드 전체를 개인 구현으로 주장하는 것은 아닙니다. 발췌에는 당시 코드의 표현과 한계를 그대로 남겼습니다.

### 게시판 목록·CRUD 구현

2023-06-13 · [`9504eb5`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/9504eb5d65938a680eefd3c58d865991bb0a9da3) · 원본 메시지: `board init`

문자열만 반환하던 게시판 뷰를 게시글 목록·작성·상세·수정·삭제 처리로 확장했습니다. 아래는 목록 조회와 페이지네이션을 추가한 부분입니다.

변경 파일: `board/views.py` · [현재 코드](../board/views.py)

```diff
+def index(request):
+    page = request.GET.get('page', '1')  # 페이지 파라미터 얻기, 없으면 1
+    board_list = Board.objects.order_by('-id')
+
+    # 페이징 처리
+    paginator = Paginator(board_list, 10)  # 페이지당 10개씩 보여주기
+    page_obj = paginator.get_page(page)  # page에 해당하는 페이징 객체 생성

+    context = {'board_list': page_obj}   # 페이징 객체(page_obj) 전달
+    return render(request, 'boards/index.html', context)

-def index(request):
-    return HttpResponse("board page")
\ No newline at end of file
+
```

### 게시글 작성자 확인 추가

2023-06-14 · [`b2d4ce3`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/b2d4ce30af98edd19dd5cab1de839de4f3d7ce61) · 원본 메시지: `board member edit/delete function added`

게시글 삭제 전에 로그인 여부와 현재 사용자가 작성자인지 확인하는 조건을 추가했습니다. 같은 커밋에서 수정 처리의 작성자 확인 및 댓글 작성 처리도 추가했습니다.

변경 파일: `board/views.py` · [현재 코드](../board/views.py)

```diff
 def delete(request, pk):
     post = get_object_or_404(Board, id=pk)
-    post.delete()
-    return redirect('boards:index')
+    if request.user.is_authenticated:
+        if request.user == post.author:
+            post.delete()
+            return redirect('boards:index')
+
+    return redirect('boards:detail', post.pk)
+
```

### 영수증·주문 모델 연결

2023-06-26 · [`e804f8b`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/e804f8bbe2f47302fb75a6d968387124d206f62f) · 원본 메시지: `receipt, order DB added / payment history page added and function added / payment failed, complete function added / etc.`

상품명·금액·수량을 저장하는 영수증 모델을 수정하고, 회원·영수증을 참조하는 주문 모델과 UUID 주문 식별자를 추가했습니다. 같은 커밋의 payment/views.py에는 영수증 저장과 주문 생성 처리도 포함됩니다.

변경 파일: `payment/models.py` · [현재 코드](../payment/models.py)

```diff
diff --git a/payment/models.py b/payment/models.py
index 51977d2..88e7e81 100644
--- a/payment/models.py
+++ b/payment/models.py
@@ -1,2 +1,3 @@
 from django.db import models
+import uuid

@@ -27,12 +28,11 @@ class CostcoPrice(models.Model):
 class receipt(models.Model):
-    idx = models.BigAutoField(primary_key=True)
+    names = models.TextField(null=True)
+    price = models.TextField(null=True)
+    count_quantity = models.TextField(null=True)
+    member = models.ForeignKey("member.User", on_delete = models.CASCADE)
+
+class Order(models.Model):
     date = models.DateTimeField(auto_now_add = True)
-    names = models.CharField(max_length=50)
-    price = models.CharField(max_length=50)
+    Order_id = models.UUIDField(default=uuid.uuid4, editable=False)
     member = models.ForeignKey("member.User", on_delete = models.CASCADE)
-    count_quantity = models.IntegerField()
-
-    class Meta:
-        managed = False
-        db_table = 'payment_receipt'
-
\ No newline at end of file
+    receipts = models.ForeignKey(receipt, on_delete=models.CASCADE)
\ No newline at end of file
```

### 상품 인식 요청의 로그인 확인

2023-06-27 · [`2ddf688`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/2ddf688226ea55603f06f5ab79e19891266a340b) · 원본 메시지: `top bar product recognition only member access`

상품 인식 결과를 처리하는 조건에 로그인 여부 확인을 추가했습니다. 공통 메뉴 템플릿에도 비로그인 사용자에게 로그인 안내를 표시하는 처리를 추가했습니다.

변경 파일: `payment/views.py` · [현재 코드](../payment/views.py)

```diff
diff --git a/payment/views.py b/payment/views.py
index bf2e63a..4b1fedd 100644
--- a/payment/views.py
+++ b/payment/views.py
@@ -1,2 +1,2 @@
-from django.shortcuts import render
+from django.shortcuts import render, redirect
 from django.utils import timezone
@@ -20,3 +20,3 @@ def index(request):
 def result(request):
-    if request.method == 'POST' and request.FILES['files']:
+    if request.method == 'POST' and request.FILES['files'] and request.user.is_authenticated:

@@ -95,3 +95,3 @@ def result(request):
     else:
-        return render(request, 'payment/fail.html', context)
+        return render(request, 'payment/fail.html')
```

### 구매 내역 정렬·페이지네이션

2023-06-28 · [`5f2ef87`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/5f2ef871b76c40dbb59f22f0dda5f3dcd5182f10) · 원본 메시지: `bug fixed, order_list page function added`

회원별 주문 조회에 최신순 정렬과 페이지네이션을 추가하고, 구매 내역 템플릿에 페이지 이동과 목록 번호 계산을 반영했습니다. 발췌는 해당 커밋 당시 코드로, 현재 공개 소스에서는 페이지 크기가 이후 변경되어 있습니다.

변경 파일: `member/views.py` · [현재 코드](../member/views.py)

```diff
-    Orders = Order.objects.filter(member=request.user)
+    Order_list = Order.objects.filter(member=request.user).order_by('-id')
+
+    # 페이지 파라미터 얻기, 없으면 1
+    page = request.GET.get('page', '1')
+
+    # 페이지당 10개씩 보여주기
+    paginator = Paginator(Order_list, 10)
+    page_obj = paginator.get_page(page)
```

### QR 이미지 생성·결과 화면 연동

2023-06-28 · [`1d72bdd`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/1d72bdd64cb5e233aeda29331ffd969761fc2264) · 원본 메시지: `qr code added`

상품명 목록을 QR 코드로 만들고, 생성한 PNG를 Base64로 변환해 결과 화면에 전달했습니다. 같은 커밋의 결과 템플릿에는 qr_code_image를 표시하는 img 요소를 추가했습니다. 이 변경에서 QR에 넣는 값은 상품명 목록입니다.

변경 파일: `payment/views.py` · [현재 코드](../payment/views.py)

```diff
+        url = name_list
+        qr = qrcode.QRCode(
+            version=1,
+            error_correction=qrcode.constants.ERROR_CORRECT_L,
+            box_size=20,
+            border=10,
+        )
+        qr.add_data(url)
+        qr.make(fit=True)
+
+        img = qr.make_image(fill_color="black", back_color="white")
+        # qr_img = qrcode.make(url)
+        # qr_img.save('static/img/qr_test2.png'
+
```

## 확인 범위

- 작성자별 코드 변경 기록이며, 팀 전체의 기능·모델·설계를 단독 수행했다는 의미는 아닙니다.
- 실행 성능, 운영 성과, 모델 정확도 등 측정 근거가 없는 수치는 기재하지 않았습니다.
- 원본은 Private이므로 원본 커밋 링크를 외부인이 열 수 없을 수 있습니다. 공개된 문서·발췌 코드 자체가 원본 이력에 대한 독립적인 인증 수단은 아닙니다.
- 전체 원본 이력, DB, 인증정보는 이 문서에 포함하지 않았습니다.
