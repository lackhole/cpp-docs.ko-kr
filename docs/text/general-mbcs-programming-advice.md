---
title: 일반적인 MBCS 프로그래밍 팁
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
ms.openlocfilehash: 31c17d6d6dee49f75f5cd8f84aa0690e649aa509
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410683"
---
# <a name="general-mbcs-programming-advice"></a>일반적인 MBCS 프로그래밍 팁

다음의 MBCS 프로그래밍 팁을 참고하세요.

- 코드의 유연성을 위해 가급적 `_tcschr`나 `_tcscpy`와 같은 런타임 매크로를 사용하세요. 자세한 내용은 [tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)을 참조하십시오.

- C 런타임의 `_getmbcp` 함수는 현재 코드 페이지 정보를 가져옵니다.

- 공간 낭비를 줄이기 위한 목적으로 문자열 리소스에 포함된 다른 곳에서 사용하는 문자열을 다시 사용하지 마십시오. 대상 언어에 따라 번역 과정을 거치면서 재사용한 문자열이 다른 의미를 가질 수 있습니다. 예를 들어 응용 프로그램 주 메뉴의 File'이 번역된 '파일'은 대화상자의 'File' 문자열과 다르게 번역될 수 있습니다. 동일한 이름을 가진 둘 이상의 문자열을 사용하는 경우 각 문자열마다 다른 문자열 ID를 사용합니다.

- 응용 프로그램이 멀티바이트 문자 집합(MBCS)을 지원하는 운영 체제에서 실행 중인지 알아야 하는 경우에는, 이렇게 하려면 프로그램 시작; 플래그를 설정 API 호출에 의존 하지 않습니다.

- 대화 상자를 디자인할 때 멀티바이트 문자 집합(MBCS) 변환을 위해 정적 텍스트 컨트롤 끝 부분에 약 30% 정도의 추가 공간을 확보하세요.

- 일부 글꼴은 모든 시스템에서 사용하지 못할 수도 있으므로, 애플리케이션에서 글꼴을 사용할 때 주의해야 합니다.

- 대화 상자의 글꼴 선택시 MS Sans Serif나 Helvetica 대신 [MS Shell Dlg](/windows/desktop/Intl/using-ms-shell-dlg-and-ms-shell-dlg-2)를 선택합니다. MS Shell Dlg는 대화 상자를 생성시 시스템에서 올바른 글꼴로 바뀝니다. MS Shell Dlg 사용하면 운영 체제 시스템마다 변경될 수 있는 모든 사항을 자동으로 적용할 수 있습니다. (MFC는 MS Shell Dlg를 DEFAULT_GUI_FONT로 변경합니다. Windows 95, Windows 98 및 Windows NT 4는 시스템 글꼴로 바꿉니다.해당 시스템에서는 MS Shell Dlg를 올바르게 처리하지 못하기 때문입니다.)

- 응용 프로그램을 디자인할 때 어떤 문자열을 지역화할 수 있는지를 결정합니다. 확실하지 않은 경우 주어진 문자열은 지역화될 것이라고 가정합니다. 지역화 가능한 문자열과 그렇지 않은 문자열을 혼용하지 마세요.

## <a name="see-also"></a>참고자료

[멀티바이트 문자 집합(MBCS) 프로그래밍 팁](../text/mbcs-programming-tips.md)<br/>
[포인터 증가 및 감소](../text/incrementing-and-decrementing-pointers.md)
