---
title: AFX_EXTENSION_MODULE 구조체
ms.date: 11/04/2016
f1_keywords:
- AFX_EXTENSION_MODULE
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
ms.openlocfilehash: e1bdc9d744424ab0ad59be3bd7b815b5122bcd10
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338638"
---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE 구조체

`AFX_EXTENSION_MODULE` MFC 확장명 Dll의 초기화 하는 동안 MFC 확장명 DLL 모듈의 상태를 저장 하는 데 사용 됩니다.

## <a name="syntax"></a>구문

```
struct AFX_EXTENSION_MODULE
{
    BOOL bInitialized;
    HMODULE hModule;
    HMODULE hResource;
    CRuntimeClass* pFirstSharedClass;
    COleObjectFactory* pFirstSharedFactory;
};
```

#### <a name="parameters"></a>매개 변수

*bInitialized*<br/>
DLL 모듈을 사용 하 여 초기화 되었으면 TRUE `AfxInitExtensionModule`합니다.

*hModule*<br/>
DLL 모듈 핸들을 지정 합니다.

*hResource*<br/>
DLL 사용자 지정 리소스 모듈의 핸들을 지정 합니다.

*pFirstSharedClass*<br/>
정보에 대 한 포인터 (의 `CRuntimeClass` 구조) DLL 모듈의 첫 번째 런타임 클래스에 대 한 합니다. 런타임 클래스 목록의 시작 부분을 제공 하는 데 사용 합니다.

*pFirstSharedFactory*<br/>
DLL 모듈의 첫 번째 개체 팩터리에 대 한 포인터 (한 `COleObjectFactory` 개체). 클래스 팩터리 목록의 시작 부분을 제공 하는 데 사용 합니다.

## <a name="remarks"></a>설명

MFC 확장명 Dll에서 두 가지를 수행 해야 해당 `DllMain` 함수:

- 호출 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) 반환 값을 확인 합니다.

- 만들기는 `CDynLinkLibrary` DLL를 내보내는 경우 개체 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체 또는 고유한 사용자 지정 리소스가 있습니다.

합니다 `AFX_EXTENSION_MODULE` 구조는 MFC 확장명 DLL 모듈 상태를 실행 하기 전에 일반적인 정적 개체 생성의 일부로 MFC 확장 DLL에 의해 초기화 된 런타임 클래스 개체의 복사본을 포함 하 여의 복사본을 저장 하는 데 사용 됩니다 `DllMain` 는 입력 합니다. 예를 들어:

[!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]

저장 된 모듈 정보를 `AFX_EXTENSION_MODULE` 구조를 복사할 수는 `CDynLinkLibrary` 개체입니다. 예를 들어:

[!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)<br/>
[AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)
