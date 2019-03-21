---
title: HTML 기초
ms.date: 11/04/2016
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
ms.openlocfilehash: 63a866786abc3b1eaa87a06492b43b1c9e354882
ms.sourcegitcommit: 90817d9d78fbaed8ffacde63f3add334842e596f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58278387"
---
# <a name="html-basics"></a>HTML 기초

대부분의 브라우저는 검색 중인 페이지의 HTML 소스를 검사 하는 기능이 있습니다. HTML (Hypertext markup language) 태그 수가 표시 됩니다는 소스를 보면 텍스트를 사용 하 여 섞어서 꺾쇠 괄호 (<>) 둘러싸여 있습니다.

간단한 웹 페이지 작성을 HTML 태그를 사용 하는 다음 단계를 수행 합니다. 이 단계에서는 있습니다에서는 메모장에서 파일에 일반 텍스트를 입력, 몇 가지 변경, 파일을 저장 및 변경 사항을 확인 하려면 브라우저에서 페이지를 다시 로드 합니다.

#### <a name="to-create-an-html-file"></a>HTML 파일을 만들려면

1. 메모장 또는 일반 텍스트 편집기를 엽니다.

1. **파일** 메뉴 선택 **새로 만들기**합니다.

1. 다음 줄을 입력 합니다.

```
<HTML>
<HEAD>
<TITLE>Top HTML Tags</TITLE>
</HEAD>
</HTML>
```

1. 합니다 **파일** 메뉴에서 선택 **저장**, c:\webpages\First.htm로 파일을 저장 합니다. 파일을 편집기에서 열어 둡니다.

1. 브라우저와 스위치를 **파일** 메뉴 선택 **열기**, 또는 형식 *file://C:/webpages/first.htm* 브라우저의 URL 편집 상자에 합니다. 창 캡션에 "최상위 HTML 태그입니다."를 사용 하 여 빈 페이지가 표시 됩니다.

   태그 쌍 및 꺾쇠 괄호에 포함시킬지 확인 합니다. 태그는 대/소문자를 구분 하지 않지만 대/소문자가 태그를 강조 하기 위해 종종 사용 됩니다.

   태그 \<HTML > 태그와 문서 시작 \</HTML > 종료 합니다. 끝 태그 (항상 필수는 아님) 시작 태그와 동일 하지만 태그 앞에 슬래시 (/)가 있습니다. 꺾쇠 괄호 (<) 및 태그의 시작 부분 사이 공백이 없어야 합니다.

1. 메모장으로 전환한 후는 \<헤드/> 줄을 입력 합니다.

```
<BODY>
    HTML is swell.
    Life is good.
</BODY>
```

1. **파일** 메뉴 선택 **저장**합니다.

1. 브라우저가로 다시 전환 하 고 페이지를 새로 고칩니다.

   브라우저 창의 클라이언트 영역에 표시 됩니다. 에 캐리지 리턴는 무시 됩니다. 줄 바꿈을 할 경우에 포함 해야는 `<BR>` 이후 첫 번째 줄은 태그입니다.

   에 따라, 사이 아무 곳 이나 텍스트를 삽입 하는 모든 단계에 대 한 \<본문 > 및  \< /B > 문서의 본문에 추가 합니다.

9. 헤더를 추가 합니다.

```
<H3>Here's the big picture</H3>
```

10. 페이지와 같은 디렉터리에 저장 하는.gif 파일을 사용 하 여 이미지를 추가 합니다.

```
<IMG src="yourfile.gif">
```

11. 목록을 추가 합니다.

```
<UL>Make me an unordered list.
<LI>One programmer</LI>
<LI>Ten SDKs</LI>
<LI>Great Internet Apps</LI>
</UL>
```

12. 목록 대신 숫자를 사용 하 여 쌍을 이루는 \<OL > 및 \</o L > 자리에 태그를 \<u L > 및  \< /u L > 태그입니다.

시작 가져와야 합니다. 웹 페이지에 매우 유용한 기능을 표시 하는 경우 HTML 소스를 검사 하 여 만들어진 방법 확인할 수 있습니다. Microsoft 프런트 페이지와 같은 HTML 편집기 간단 하 고 고급 페이지를 만드는 데 사용할 수 있습니다.

구축한 경험이 파일의 전체 HTML 소스는 다음과 같습니다.

```
<HTML>
<HEAD>
<TITLE>Top HTML Tags</TITLE>
</HEAD>
<BODY>
HTML is swell.<BR>
Life is good.
<H3>Here's the big picture</H3>
<IMG src="yourfile.gif">
<UL>Make me an unordered list.
<LI>One programmer</LI>
<LI>Ten SDKs</LI>
<LI>Great Internet Apps</LI>
</UL>
</BODY>
</HTML>
```

태그, 특성 및 확장의 전체 내용은 (HTML) 사양을 참조 하십시오.

[HTML의 최신 게시 된 버전](https://www.w3.org/TR/html/) W3C.org에서.

## <a name="see-also"></a>참고자료

[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)
