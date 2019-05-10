---
title: 문자열 변환 매크로
ms.date: 11/04/2016
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
ms.openlocfilehash: 889f8459e81418197420bc2efd410225d4f220bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197257"
---
# <a name="string-conversion-macros"></a>문자열 변환 매크로

이러한 매크로 문자열 변환 기능을 제공합니다.

##  <a name="atl_and_mfc_string_conversion_macros"></a>  ATL 및 MFC 문자열 변환 매크로

이 항목에서 설명하는 문자열 변환 매크로는 ATL과 MFC에 모두 사용 가능합니다. MFC 문자열 변환에 대 한 자세한 내용은 참조 하세요. [TN059: MFC/유니코드 변환 매크로 사용 하 여](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) 하 고 [MFC 매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)합니다.

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>  DEVMODE 및 TEXTMETRIC 문자열 변환 매크로

이러한 매크로의 복사본을 만듭니다는 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 하거나 [TEXTMETRIC](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica) 구조체이 고 새 구조 내에서 문자열을 새 문자열 형식으로 변환 합니다. 매크로 새 구조에 대 한 스택에 메모리를 할당 하 고 새 구조에 대 한 포인터를 반환 합니다.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>설명

예를 들어:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

and:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

매크로 이름을 원본 구조에서의 문자열 형식은 왼쪽입니다 (예를 들어 **A**) 및 대상 구조에 문자열 형식은 오른쪽 (예를 들어 **W**). **A** LPSTR에 대 한 의미 **OLE** LPOLESTR는 **T** LPTSTR에 대 한 의미 및 **W** LPWSTR는 의미입니다.

따라서 DEVMODEA2W 복사를 `DEVMODE` LPSTR 구조체에 문자열을 `DEVMODE` 문자열 LPWSTR TEXTMETRICOLE2T 복사본을 사용 하 여 구조를 `TEXTMETRIC` 구조 LPOLESTR 사용 하 여 문자열을 `TEXTMETRIC` LPTSTR 문자열이 포함 된 구조체 등에.

변환 하는 두 문자열을 `DEVMODE` 구조는 장치 이름 (`dmDeviceName`) 및 형식 이름 (`dmFormName`). 합니다 `DEVMODE` 문자열 변환 매크로 구조체의 크기가 업데이트 (`dmSize`).

변환에서 4 개의 문자열을 `TEXTMETRIC` 구조는 첫 번째 문자 (`tmFirstChar`), 마지막 문자 (`tmLastChar`), 기본 문자 (`tmDefaultChar`), 및 줄바꿈 문자 (`tmBreakChar`).

동작을 `DEVMODE` 및 `TEXTMETRIC` 있는 경우 문자열 변환 매크로 적용 중인 컴파일러 지시문에 따라 다릅니다. 소스와 대상 형식이 같으면 변환이 수행되지 않습니다. 컴파일러 지시문을 변경 **T** 하 고 **OLE** 다음과 같습니다.

|적용되는 컴파일러 지시문|T의 변경 결과|OLE의 변경 결과|
|----------------------------------|---------------|-----------------|
|없음|**A**|**W**|
|**\_UNICODE**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|**\_유니코드** 고 **OLE2ANSI**|**W**|**A**|

다음 표에서 `DEVMODE` 고 `TEXTMETRIC` 문자열 변환 매크로입니다.

|||
|-|-|
|DEVMODEA2W|TEXTMETRICA2W|
|DEVMODEOLE2T|TEXTMETRICOLE2T|
|DEVMODET2OLE|TEXTMETRICT2OLE|
|DEVMODEW2A|TEXTMETRICW2A|

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)
