---
title: 스크립트 (ATL) 호출
ms.date: 11/04/2016
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
ms.openlocfilehash: 6ca744ced53677550e7b77f44d4f6550da744372
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820561"
---
# <a name="invoking-scripts"></a>스크립트 호출

[대체 가능 매개 변수 (The 등록자 전처리기)를 사용 하 여](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 대체 지도 설명 하 고 등록 기관 메서드를 언급 **AddReplacement**합니다. 등록 기관은 스크립팅 관련 다른 메서드를 8 개 있으며 다음 표에 설명 되어 모든.

|메서드|구문/설명|
|------------|-------------------------|
|**ResourceRegister**|**HRESULT ResourceRegister( LPCOLESTR**  *resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType` **);**<br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 합니다. *resFileName* 모듈 자체에 UNC 경로 나타냅니다. *nID* 하 고 *szType* 각각 리소스의 ID 및 형식을 포함 합니다.|
|**ResourceUnregister**|**HRESULT ResourceUnregister( LPCOLESTR**  *resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType` **);**<br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 취소 합니다. *resFileName* 모듈 자체에 UNC 경로 나타냅니다. *nID* 하 고 *szType* 각각 리소스의 ID 및 형식을 포함 합니다.|
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz( LPCOLESTR**  *resFileName* **, LPCOLESTR**  *szID* **, LPCOLESTR**  `szType` **);**<br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 합니다. *resFileName* 모듈 자체에 UNC 경로 나타냅니다. *szID* 하 고 *szType* 각각 리소스의 문자열 식별자 및 형식을 포함 합니다.|
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz( LPCOLESTR**  *resFileName* **, LPCOLESTR**  *szID* **, LPCOLESTR**  `szType` **);**<br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 취소 합니다. *resFileName* 모듈 자체에 UNC 경로 나타냅니다. *szID* 하 고 *szType* 각각 리소스의 문자열 식별자 및 형식을 포함 합니다.|
|**FileRegister**|**HRESULT FileRegister( LPCOLESTR**  *fileName*  **);**<br /><br /> 파일에 스크립트를 등록합니다. *fileName* 가 포함 되어 있습니다 (또는) 리소스 스크립트 파일에 UNC 경로입니다.|
|**FileUnregister**|**HRESULT FileUnregister( LPCOLESTR**  *fileName*  **);**<br /><br /> 파일에 스크립트 등록을 취소 합니다. *fileName* 가 포함 되어 있습니다 (또는) 리소스 스크립트 파일에 UNC 경로입니다.|
|**StringRegister**|**HRESULT StringRegister( LPCOLESTR**  *data*  **);**<br /><br /> 문자열에서 스크립트를 등록합니다. *데이터* 스크립트 자체를 포함 합니다.|
|**StringUnregister**|**HRESULT StringUnregister( LPCOLESTR**  *data*  **);**<br /><br /> 문자열에 스크립트 등록을 취소 합니다. *데이터* 스크립트 자체를 포함 합니다.|

**ResourceRegisterSz** 하 고 **ResourceUnregisterSz**, 비슷합니다 **ResourceRegister** 하 고 **ResourceUnregister**, 문자열로 지정할 수 있지만 식별자입니다.

메서드 **FileRegister** 하 고 **FileUnregister** 리소스에서 스크립트를 원하지 않는 경우 또는 해당 파일에 스크립트를 하려는 경우 유용 합니다. 메서드 **StringRegister** 하 고 **StringUnregister** .rgs 파일을 동적으로 할당 된 문자열에 저장할 수 있습니다.

## <a name="see-also"></a>참고자료

[등록자 스크립트 만들기](../atl/creating-registrar-scripts.md)
