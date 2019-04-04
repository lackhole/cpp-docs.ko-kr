---
title: CMFCRibbonApplicationButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
ms.openlocfilehash: 01b6937ee597766922597fda5664c78f75be6b67
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772165"
---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton 클래스

애플리케이션 창의 왼쪽 위 모서리에 있는 특수 단추를 구현합니다. 클릭하면 단추는 **열기** , **저장**및 **종료**와 같은 일반적인 **파일**명령이 포함된 메뉴를 엽니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|`CMFCRibbonApplicationButton` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCRibbonApplicationButton::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CMFCRibbonApplicationButton::SetImage](#setimage)|리본 응용 프로그램 단추에 이미지를 할당합니다.|

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonApplicationButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 응용 프로그램 단추에 이미지를 할당 하는 방법 및 해당 도구 설명이 설정 하는 방법을 보여 줍니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonBar.h

##  <a name="cmfcribbonapplicationbutton"></a>  CMFCRibbonApplicationButton::CMFCRibbonApplicationButton

생성 하 고 초기화 된 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) 개체입니다.

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
  CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>매개 변수

*uiBmpResID*<br/>
응용 프로그램 단추에 표시할 이미지의 리소스 ID입니다.

*hBmp*<br/>
응용 프로그램 단추에 표시할 비트맵 핸들입니다.

### <a name="remarks"></a>설명

리본 응용 프로그램 단추는 응용 프로그램 창의 왼쪽 위 모퉁이에 있는 특수 단추가입니다. 사용자가이 단추를 클릭 하면 응용 프로그램이 일반적으로 일반적인를 포함 하는 메뉴가 열립니다 **파일** 등의 명령은 **열려**합니다 **저장**, 및 **종료**.

##  <a name="setimage"></a>  CMFCRibbonApplicationButton::SetImage

응용 프로그램 단추에 이미지를 할당합니다.

```
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>매개 변수

*uiBmpResID*<br/>
[in] 응용 프로그램 단추에 표시할 이미지의 리소스 ID입니다.

*hBmp*<br/>
[in] 응용 프로그램 단추에 표시할 비트맵 핸들입니다.

### <a name="remarks"></a>설명

단추를 만든 후 새 이미지를 응용 프로그램 리본 단추에 할당 하려면이 메서드를 사용 합니다. 응용 프로그램 단추를 응용 프로그램 창의 왼쪽 위 모퉁이 있습니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)
