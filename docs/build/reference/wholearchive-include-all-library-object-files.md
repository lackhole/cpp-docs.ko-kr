---
title: /WHOLEARCHIVE (모든 라이브러리 개체 파일 포함)
ms.date: 11/04/2016
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
ms.openlocfilehash: db99816b18110b424647603196040997044e7fbd
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808653"
---
# <a name="wholearchive-include-all-library-object-files"></a>/WHOLEARCHIVE (모든 라이브러리 개체 파일 포함)

연결 된 실행 파일에서 정적 라이브러리의 모든 개체 파일을 포함 하도록 링커에 강제 합니다.

## <a name="syntax"></a>구문

> /WHOLEARCHIVE[:*library*]

## <a name="remarks"></a>설명

/WHOLEARCHIVE 옵션에 지정된 된 정적 라이브러리에서 모든 개체 파일을 포함 하거나 명령 링크를 지정 하는 모든 정적 라이브러리에서 없는 라이브러리를 지정 하는 경우 링커가 되도록 합니다. 여러 라이브러리에 대 한 /WHOLEARCHIVE 옵션을 지정 하려면 링커 명령줄에 둘 이상의 /WHOLEARCHIVE 전환 사용할 수 있습니다. 기본적으로 링커 실행 파일의 다른 개체 파일에서 참조 하는 기호를 내보내는 경우에 연결 된 출력에서 개체 파일을 포함 합니다. /WHOLEARCHIVE 옵션을 링커를 링커 명령줄에 개별적으로 지정 하는 것 처럼 정적 라이브러리에 보관 하는 모든 개체 파일을 처리할 수 있습니다.

정적 라이브러리에서 모든 기호를 다시 내보낼 /WHOLEARCHIVE 옵션을 사용할 수 있습니다. 이렇게 하면 라이브러리 코드, 리소스 및 메타 데이터의 모든 포함 되는 둘 이상의 정적 라이브러리에서 구성 요소를 만들 때 되도록 있습니다. 내보내기에 대 한 Windows 런타임 구성 요소를 포함 하는 경고 LNK4264 정적 라이브러리를 만들 때 표시 되 면 다른 구성 요소나 응용 프로그램에 해당 라이브러리를 연결 하는 경우 /WHOLEARCHIVE 옵션을 사용 합니다.

/WHOLEARCHIVE 옵션은 Visual Studio 2015 업데이트 2에서 도입 되었습니다.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **명령줄** 속성 페이지에서 **구성 속성**에 **링커**합니다.

1. /WHOLEARCHIVE 옵션을 추가 합니다 **추가 옵션** 입력란입니다.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
