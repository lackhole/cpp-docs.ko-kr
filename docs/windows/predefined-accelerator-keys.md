---
title: 액셀러레이터 키 (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.accelerator
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: bb407538f254df5f187ff91b85a8eaa753a52287
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027521"
---
# <a name="accelerator-keys-c"></a>액셀러레이터 키 (C++)

## <a name="predefined-accelerator-keys"></a>사전 정의된 액셀러레이터 키

Windows 응용 프로그램 프로젝트에 포함될 수 있는 미리 정의된 많은 액셀러레이터 키가 있습니다. 이러한 가상 키 중 일부는 Windows 환경을 위한 것입니다. 다른 브라우저 또는 유니코드 응용 프로그램을 지원 합니다. 모든 액셀러레이터에 이러한 키 중 하나를 사용할 수 있습니다.

|Key|설명|
|---------|-----------------|
|VK_ACCEPT|(IME)에 동의|
|VK_BROWSER_BACK|(Windows) 브라우저 **다시** 키|
|VK_BROWSER_FAVORITES|(Windows) 브라우저 **즐겨찾기** 키|
|VK_BROWSER_FORWARD|(Windows) 브라우저 **앞으로** 키|
|VK_BROWSER_HOME|(Windows) 브라우저 **시작** 하 고 **홈** 키|
|VK_BROWSER_REFRESH|(Windows) 브라우저 **새로 고침** 키|
|VK_BROWSER_SEARCH|(Windows) 브라우저 **검색** 키|
|VK_BROWSER_STOP|(Windows) 브라우저 **중지** 키|
|VK_CONVERT|(IME)으로 변환|
|VK_FINAL|최종 모드 (IME)|
|VK_HANGUEL|IME) 한글 모드 (호환성을 위해 유지 관리, 유지, VK_HANGUL 사용)|
|VK_HANGUL|IME) 한글 모드|
|VK_HANJA|IME) 한자 모드|
|VK_JUNJA|IME) 전자 모드|
|VK_KANA|IME) 일본어가 나 모드|
|VK_KANJI|IME) 간지 모드|
|VK_LAUNCH_APP1|(Windows) **응용 프로그램 1 시작** 키|
|VK_LAUNCH_APP2|(Windows) **응용 프로그램 2 시작** 키|
|VK_LAUNCH_MAIL|(Windows) **시작 메일** 키|
|VK_LAUNCH_MEDIA_SELECT|(Windows) **미디어 선택** 키|
|VK_LCONTROL|**왼쪽 Ctrl** 키|
|VK_LMENU|**왼쪽 메뉴** 키|
|VK_LSHIFT|**왼쪽 Shift** 키|
|VK_MEDIA_NEXT_TRACK|(Windows) **다음 트랙** 키|
|VK_MEDIA_PLAY_PAUSE|(Windows) **Play/Pause 미디어** 키|
|VK_MEDIA_PREV_TRACK|(Windows) **이전 트랙** 키|
|VK_MEDIA_STOP|(Windows) **미디어 중지** 키|
|VK_MODECHANGE|(입력기) 모드 변경 요청|
|VK_NONCONVERT|(IME) 변환 안 함|
|VK_OEM_1|(Windows) 미국 표준 키보드의 경우는 **;:** 키|
|VK_OEM_102|(Windows) 꺾쇠 괄호 키 또는 RT 102 키 키보드의 백슬래시 키|
|VK_OEM_2|(Windows) 미국 표준 키보드의 경우는 **/?** key|
|VK_OEM_3|(Windows) 미국 표준 키보드의 경우는 **`~** 키|
|VK_OEM_4|(Windows) 미국 표준 키보드의 경우는 **[{** 키|
|VK_OEM_5|(Windows) 미국 표준 키보드의 경우는 **\\ &#124;** 키|
|VK_OEM_6|(Windows) 미국 표준 키보드의 경우는 **]을 (를)** 키|
|VK_OEM_7|(Windows) 미국 표준 키보드의 경우 ' 작은따옴표/큰따옴표 ' 키|
|VK_OEM_COMMA|(Windows) 모든 국가/지역의 경우는 **,** 키|
|VK_OEM_MINUS|(Windows) 모든 국가/지역의 경우는 **-** 키|
|VK_OEM_PERIOD|(Windows) 모든 국가/지역의 경우는 **합니다.** key|
|VK_OEM_PLUS|(Windows) 모든 국가/지역의 경우는 **+** 키|
|VK_PACKET|(Windows) 키 입력 것 처럼 유니코드 문자를 전달 하는 데 사용 합니다.|
|VK_RCONTROL|**오른쪽 Ctrl** 키|
|VK_RMENU|**오른쪽 메뉴** 키|
|VK_RSHIFT|**오른쪽 Shift** 키|
|VK_SLEEP|**컴퓨터 절전 모드** 키|
|VK_VOLUME_DOWN|(Windows) **볼륨 작게** 키|
|VK_VOLUME_MUTE|(Windows) **볼륨 음소거** 키|
|VK_VOLUME_UP|(Windows) **볼륨 크게** 키|
|VK_XBUTTON1|(Windows) **X1** 마우스 단추|
|VK_XBUTTON2|(Windows) **X2** 마우스 단추|

## <a name="accelerator-key-association"></a>액셀러레이터 키 연결

메뉴 항목과 키보드 조합에서 동일한 프로그램 명령을 여러 번 실행하도록 하려고 합니다. 응용 프로그램의 액셀러레이터 키 테이블의 항목에 메뉴 항목을 동일한 리소스 식별자 (ID)를 할당 하 여이 작업을 수행 합니다. 그런 다음 메뉴 항목의 캡션을 편집하여 액셀러레이터 키의 이름을 표시합니다. 메뉴 항목과 액셀러레이터 키에 대 한 자세한 내용은 참조 하세요. [메뉴 명령을](../windows/associating-a-menu-command-with-an-accelerator-key.md)합니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[액셀러레이터 키 편집기](../windows/accelerator-editor.md)<br/>