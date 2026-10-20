# 개인 커밋 목록

원본 팀 저장소의 `master`에서 GitHub `author=fourevere` 필터에 해당하는 기록을 정리했습니다. 원본 커밋 해시·작성일·메시지를 기준으로 작성했으며, 날짜는 한국 시간(UTC+09:00)입니다.

- 범위: 2023-06-13 ~ 2023-06-29
- 전체 54개: 일반 커밋 40개, 병합 커밋 14개
- 다른 브랜치에만 있는 커밋은 이 목록에 포함하지 않았습니다.
- 원본 저장소는 Private이므로 원본 링크는 접근 권한이 있는 사용자만 열 수 있습니다.

[대표 구현과 코드 변경](PERSONAL_CONTRIBUTIONS.md) · [CSV 전체 목록](COMMIT_HISTORY.csv)

## 구현·수정 커밋 40개

메시지는 원문을 유지했습니다. `bug fixed`, `test`, `.`처럼 설명이 짧은 기록도 임의로 성과로 바꾸지 않았습니다. 변경 파일은 비교 범위를 보여주며, 파일 전체를 혼자 작성했다는 뜻은 아닙니다.

| 작성일 | 원본 커밋 | 원본 메시지 | 변경 파일 |
| --- | --- | --- | --- |
| 2023-06-13 | [`9504eb5`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/9504eb5d65938a680eefd3c58d865991bb0a9da3) | board init | `board/forms.py`, `board/models.py`, `board/templates/boards/detail.html`, `board/templates/boards/edit.html`, `board/templates/boards/index.html`, `board/templates/boards/new.html`, `board/urls.py`, `board/views.py` |
| 2023-06-13 | [`330e0ea`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/330e0eaf699e2366ea8ebdf79630d85ea2599027) | board index number edit | `board/templates/boards/index.html` |
| 2023-06-14 | [`de6e440`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/de6e440973721033e4a744ef6808dd5bca172149) | board index number edit | `board/templates/boards/index.html`, `board/templatetags/board_filter.py` |
| 2023-06-14 | [`66b3d48`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/66b3d486ab276669a3f46c9cc02bd4a11eacec68) | board views function add | `board/models.py`, `board/templates/boards/detail.html`, `board/templates/boards/index.html` |
| 2023-06-14 | [`86c2314`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/86c23144cb8a21d0dea2763a78acd7d00493269d) | board username fuction add | `board/forms.py`, `board/models.py`, `board/templates/boards/new.html`, `board/urls.py`, `board/views.py` |
| 2023-06-14 | [`8176b4d`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/8176b4df4e7bde4a03bc7918d4fcc82ccaa62a16) | board nickname add | `board/models.py`, `board/templates/boards/detail.html`, `board/templates/boards/index.html`, `board/views.py` |
| 2023-06-14 | [`b2d4ce3`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/b2d4ce30af98edd19dd5cab1de839de4f3d7ce61) | board member edit/delete function added | `board/forms.py`, `board/templates/boards/detail.html`, `board/templates/boards/index.html`, `board/urls.py`, `board/views.py` |
| 2023-06-14 | [`f2b7772`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/f2b7772ab56f256eb0e402ea7e9c534f989eab78) | board delete warning message added | `board/templates/boards/detail.html` |
| 2023-06-15 | [`0b5ac2e`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/0b5ac2edd476911d64ccd404170482f8e506c2ee) | . | `board/templates/boards/index.html`, `board/templates/boards/new.html` |
| 2023-06-16 | [`187122d`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/187122d1183a544d8d2a53fce8bb93f2bc28825e) | list of posts delete | `board/templates/boards/detail.html`, `board/templates/boards/new.html` |
| 2023-06-16 | [`bad67ec`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/bad67ec2544936017ecbd38e03ffe4be390063a0) | comment nickname fix | `board/templates/boards/detail.html`, `board/views.py` |
| 2023-06-16 | [`245e198`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/245e1985158430c46b3af08785cebcac737d812a) | nickname fix | `board/templates/boards/detail.html` |
| 2023-06-16 | [`1a6cb9b`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/1a6cb9b8bb7285a66413bb8d87dfc917bfa98509) | board detail UI fix | `board/templates/boards/detail.html`, `templates/base.html` |
| 2023-06-16 | [`aa74377`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/aa743773c732a93f304de08956eac5f6df170fe1) | time fix | `django_for_front/settings.py` |
| 2023-06-16 | [`bbaadad`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/bbaadad10c2f63c2de6147a13f121f49c1f5228f) | create date added, bug fix | `board/models.py`, `board/templates/boards/detail.html`, `board/templates/boards/edit.html`, `board/templates/boards/index.html` |
| 2023-06-19 | [`d4a50a9`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/d4a50a9944731d3b02458873be02abcfb8cd163b) | comment delete warning, main board top 5 fixed | `board/templates/boards/detail.html`, `board/templates/boards/index.html`, `main/models.py`, `main/templates/main/news_list.html`, `main/views.py` |
| 2023-06-19 | [`0c6dee5`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/0c6dee5399f33c5b6015b946e10acd09960d11dd) | board index character limit | `board/templates/boards/index.html` |
| 2023-06-19 | [`6a32aeb`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/6a32aebc37f9b214f5165be35274807891913f7b) | title \n added | `board/templates/boards/detail.html`, `board/templatetags/board_filter.py` |
| 2023-06-19 | [`ed24153`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/ed2415376c98d5018ab31eb3d052e9e655c922d2) | bug fixed | `board/forms.py`, `main/templates/main/news_list.html` |
| 2023-06-20 | [`27473d4`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/27473d4c2e8c99ac8bcbb487a00e79880c617a94) | test | `payment/templates/payment/result.html`, `payment/urls.py` |
| 2023-06-20 | [`841f20f`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/841f20f85644999a3658d71b9038003d926de5eb) | test2 | `payment/views.py` |
| 2023-06-21 | [`79ceef8`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/79ceef8e609ad380317ae7768e82c4063b7bd9cf) | requirements.txt added | `requirements.txt` |
| 2023-06-22 | [`7ecb2fd`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/7ecb2fd1237e416347c5a7b96862388fbb2481d1) | ngnok added | `ngrok.exe`, `requirements.txt` |
| 2023-06-23 | [`ec2dc77`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/ec2dc77d8765b884de7fb573ec9b036a33c6daff) | weight added | `payment/models.py`, `products_price/costco_price.csv`, `products_price/csv_to_mysql.py` |
| 2023-06-23 | [`83ba58c`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/83ba58cc4df0cb4917f494d6726b6418a070103f) | main added | `main/__init__.py`, `main/admin.py`, `main/apps.py`, `main/models.py`, `main/templates/main/news_list.html`, `main/tests.py`, `main/urls.py`, `main/views.py` |
| 2023-06-23 | [`a97f580`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/a97f5800615cb62acae050f4231c375bd1ea758c) | receipt added | `payment/models.py`, `payment/templates/payment/result.html`, `payment/views.py` |
| 2023-06-26 | [`e804f8b`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/e804f8bbe2f47302fb75a6d968387124d206f62f) | receipt, order DB added<br>payment history page added and function added<br>payment failed, complete function added<br>etc. | `member/templates/account/mypage.html`, `member/templates/account/myreceipt.html`, `member/urls.py`, `member/views.py`, `payment/models.py`, `payment/templates/payment/fail.html`, `payment/templates/payment/result.html`, `payment/urls.py`, `payment/views.py` |
| 2023-06-26 | [`4de6cac`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/4de6cac9ec6e1ed0d3ccb33b58a93c12669b8cde) | member bug fixed | `member/templates/account/mypage.html`, `member/urls.py` |
| 2023-06-26 | [`efafc75`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/efafc75cfd55ebb5f8068b65c5c38c7f0376b01c) | unnecessary models delete | `payment/models.py`, `payment/views.py` |
| 2023-06-26 | [`5ae34b3`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/5ae34b31c510b6a3c072c05c2b86c60917594eb6) | top bar product recognition function added | `static/css/style.css`, `templates/base.html` |
| 2023-06-27 | [`7f66bc0`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/7f66bc03363abdae35e476b5cd0523faa00fd31a) | top bar product recognition function fixed | `payment/views.py`, `templates/base.html` |
| 2023-06-27 | [`2ddf688`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/2ddf688226ea55603f06f5ab79e19891266a340b) | top bar product recognition only member access | `payment/views.py`, `templates/base.html` |
| 2023-06-27 | [`3c095ee`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/3c095ee2ec422c6ccbb877c1e11338c189989f42) | base fixed | `templates/base.html` |
| 2023-06-28 | [`b43cfb4`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/b43cfb4e070a8a5b2f549c07bb3b6d5d3a6ddf5a) | bug fixed | `main/templates/main/news_list.html`, `templates/base.html` |
| 2023-06-28 | [`f9bb68e`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/f9bb68ee1d69140ad230ede52f36f897438e4965) | bug fixed | `main/templates/main/news_list.html` |
| 2023-06-28 | [`51e247e`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/51e247e24e1fc0c24e8afd80251b3bb471ab8e61) | bug fixed. | `payment/views.py` |
| 2023-06-28 | [`5f2ef87`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/5f2ef871b76c40dbb59f22f0dda5f3dcd5182f10) | bug fixed, order_list page function added | `member/templates/account/mypage_payment.html`, `member/views.py`, `templates/base.html` |
| 2023-06-28 | [`1d72bdd`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/1d72bdd64cb5e233aeda29331ffd969761fc2264) | qr code added | `payment/templates/payment/result.html`, `payment/views.py` |
| 2023-06-28 | [`1382136`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/138213657c83cb673817a9f5e69468f608525eea) | requirements 추가 | `django_for_front/settings.py`, `requirements.txt` |
| 2023-06-29 | [`cbc7abf`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/cbc7abf1a55abd3bd3e4bc8a80e000c65db11e1b) | mypagepayment page index fieed | `member/templates/account/mypage_payment.html`, `member/views.py` |

## 병합 커밋 14개

아래는 다른 브랜치의 변경을 병합한 협업 기록입니다. 병합된 코드 전체를 개인 구현으로 계산하지 않았습니다.

| 작성일 | 원본 커밋 | 원본 메시지 |
| --- | --- | --- |
| 2023-06-14 | [`2c7c340`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/2c7c3401d0b4f52b9f1d00b7d4986cae69a73a64) | Merge pull request #1 from KrswJo/test_version<br><br>gg |
| 2023-06-16 | [`c194577`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/c194577e7ba41239f66d4c1aa33716cec82baa2a) | Merge pull request #2 from KrswJo/test_board<br><br>fix board bug |
| 2023-06-16 | [`7a4689a`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/7a4689a9b9b9b65f7208b0c59c36061af0d35411) | Merge branch 'master' into dev |
| 2023-06-16 | [`23909b1`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/23909b115be5981514e804ac79e9dd1bc9845dea) | Merge pull request #4 from KrswJo/dev<br><br>design detail.html, fix comments func, add log option settings.py |
| 2023-06-16 | [`edab880`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/edab880afd40cc2dc5410c52a2a58eb434bab0c5) | Merge pull request #5 from KrswJo/dev<br><br>add resisgtered DateTime, modify prototype index.html |
| 2023-06-19 | [`956ca82`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/956ca82f10635098d2a3391f918095bad7110f40) | Merge pull request #7 from KrswJo/dev<br><br>UI 관련 패치 |
| 2023-06-21 | [`6691ec6`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/6691ec6cffa7c1e1fa121dae196da6e5f6dc27b6) | Merge branch 'master' of https://github.com/KrswJo/aivle_ai_3rd_13th_big |
| 2023-06-23 | [`9a3cf21`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/9a3cf2158f7289e69aef711094ac2bdd746716af) | Merge branch 'master' of https://github.com/KrswJo/aivle_ai_3rd_13th_big |
| 2023-06-23 | [`8faf8a4`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/8faf8a4a520505f91f14f33791058bc1a77864c0) | Merge branch 'master' of https://github.com/KrswJo/aivle_ai_3rd_13th_big |
| 2023-06-23 | [`0569d22`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/0569d228eacd49ce5fcbd742fdc2441be7f356ac) | Merge branch 'master' of https://github.com/KrswJo/aivle_ai_3rd_13th_big |
| 2023-06-23 | [`4a58dfe`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/4a58dfe8b8a604600362f5261af9cb922c966f09) | Merge branch 'master' of https://github.com/KrswJo/aivle_ai_3rd_13th_big |
| 2023-06-27 | [`8557d75`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/8557d7503980efaaa40ea6568c7b2af4112b62da) | Merge branch 'pr' of https://github.com/KrswJo/aivle_ai_3rd_13th_big |
| 2023-06-27 | [`2a18e19`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/2a18e19613e36249e50815bed54f78b88e8742fb) | Merge branch 'master' of https://github.com/KrswJo/aivle_ai_3rd_13th_big |
| 2023-06-27 | [`30e9450`](https://github.com/KrswJo/aivle_ai_3rd_13th_big_project/commit/30e9450ae6b3c867837116843ebdc14362415b05) | Merge branch 'master' of https://github.com/KrswJo/aivle_ai_3rd_13th_big |

## 기록 기준

- 기준 원본 master: `9223f51ced4a1ceb0069ad9c1bba0dead954448a`
- 정리일: 2026-10-20
- 작성자 이름은 `fourevere` 또는 `gwang geun`으로 기록되어 있으며, 원본 GitHub 작성자 필터 결과와 전체 해시 목록을 대조했습니다.
- 이 문서·CSV는 개발 기록을 정리한 자료입니다. 원본 Git 객체나 전자서명에 대한 독립 검증을 대신하지 않습니다.
- 원본 커밋의 부모 이력과 다른 팀원의 커밋은 공개 저장소로 가져오지 않았습니다.
