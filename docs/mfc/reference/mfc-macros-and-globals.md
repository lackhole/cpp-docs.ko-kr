---
title: MFC 매크로 및 전역
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions [MFC]
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
ms.openlocfilehash: 86fbda42d97c9086a3c1d021618a4694cfade7df
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611801"
---
# <a name="mfc-macros-and-globals"></a>MFC 매크로 및 전역

Microsoft Foundation Class 라이브러리를 두 가지 주요 섹션으로 나눌 수 있습니다. (1) MFC 클래스 및 (2) 매크로 및 전역 함수 또는 변수가 없는 경우 클래스의 멤버, 전역 함수 또는 변수는 합니다.

MFC 라이브러리와 액티브 템플릿 라이브러리 (ATL) 문자열 변환 매크로 공유합니다. 자세한 내용은 [문자열 변환 매크로](../../atl/reference/string-conversion-macros.md) ATL 설명서에서.

MFC 매크로 및 전역 다음 범주에는 기능을 제공합니다.

## <a name="general-mfc"></a>일반 MFC

- [데이터 형식](data-types-mfc.md)

- [MFC 클래스 개체의 형식 캐스팅](type-casting-of-mfc-class-objects.md)

- [런타임 개체 모델 서비스](run-time-object-model-services.md)

- [진단 서비스](diagnostic-services.md)

- [예외 처리](exception-processing.md)

- [CString 서식 지정 및 메시지 상자 표시](cstring-formatting-and-message-box-display.md)

- [메시지 맵](message-map-macros-mfc.md)

- [대리자 및 인터페이스 맵](delegate-and-interface-maps.md)

- [모듈 및 DLL](extension-dll-macros.md)

- [응용 프로그램 정보 및 관리](application-information-and-management.md)

- [표준 명령 및 창 Id](standard-command-and-window-ids.md)

- [컬렉션 클래스 도우미](collection-class-helpers.md)

- [회색 및 디더링된 비트맵 함수](gray-and-dithered-bitmap-functions.md)

- [표준 대화 상자 데이터 교환 루틴 (DDX)](standard-dialog-data-exchange-routines.md)

- [표준 대화 상자 데이터 유효성 검사 (DDV) 루틴](standard-dialog-data-validation-routines.md)

- [AFX 메시지](afx-messages.md)

- [ToolBar 컨트롤 스타일](toolbar-control-styles.md)

- [CMFCImagePaintArea::IMAGE_EDIT_MODE 열거형](cmfcimagepaintarea-image-edit-mode-enumeration.md)

## <a name="database"></a>데이터베이스

- [레코드 필드 교환 (RFX () 함수](record-field-exchange-functions.md) 하 고 [대량 레코드 필드 교환 (대량 RFX) 함수](record-field-exchange-functions.md) MFC ODBC 클래스

- [레코드 필드 교환 (DFX) 함수](record-field-exchange-functions.md) MFC DAO 클래스

- [CRecordView 및 CDaoRecordView에 대 한 대화 상자 데이터 교환 (DDX) 함수](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (MFC ODBC와 DAO 클래스)

- [OLE 컨트롤에 대 한 대화 상자 데이터 교환 (DDX) 함수](dialog-data-exchange-functions-for-ole-controls.md)

- [매크로 및 개방형 데이터베이스 연결 (ODBC) API 함수 직접 호출 하는 데 도움이 되는 전역](database-macros-and-globals.md)

- [DAO 데이터베이스 엔진 초기화 및 종료](dao-database-engine-initialization-and-termination.md)

## <a name="internet"></a>인터넷

- [인터넷 URL 전역 구문 분석](internet-url-parsing-globals.md)

## <a name="dhtml--dhtml-event-maps"></a>DHTML / DHTML 이벤트 맵

- [DHTML 대화 상자 데이터 교환 (DDX) 도우미 매크로](ddx-dhtml-helper-macros.md)

- [DHTML 이벤트 맵](dhtml-event-maps.md)

## <a name="ole"></a>OLE

- [OLE 초기화](ole-initialization.md)

- [응용 프로그램 제어](application-control.md)

- [디스패치 맵](dispatch-maps.md)

MFC는 호출 된 함수를 제공 하는 또한 [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) 는 완벽 하 게 지원 하려면 MFC 4.0을 사용 하 여 OLE 컨테이너 개발 하면 OLE 컨트롤을 포함 하는 합니다.

## <a name="ole-controls"></a>OLE 컨트롤

- [가변 매개 변수 형식 상수](variant-parameter-type-constants.md)

- [형식 라이브러리 액세스](type-library-access.md)

- [속성 페이지](property-pages-mfc.md)

- [이벤트 맵](event-maps.md)

- [이벤트 싱크 맵](event-sink-maps.md)

- [연결 맵](connection-maps.md)

- [OLE 컨트롤 등록](registering-ole-controls.md)

- [클래스 팩터리 및 라이선스](class-factories-and-licensing.md)

- [OLE 컨트롤의 지 속성](persistence-of-ole-controls.md)

이 섹션의 첫 번째 부분은 간단 하 게 각 이전 범주에 설명 하 고 전역 및 범주에 대 한 간략 한 설명은 기능와 함께 매크로 나열 합니다. 이 전역 함수, 전역 변수 및 MFC 라이브러리의 매크로 설명입니다.

> [!NOTE]
>  대부분의 전역 함수가 "Afx" 접두사로 시작 하지만이 규칙을 따르지 않는 일부 예를 들어 대화 상자 데이터 교환 (DDX) 함수 및 많은 데이터베이스 기능을 합니다. 모든 전역 변수 "afx" 접두사로 시작합니다. 매크로 특정 접두사로 시작 되지 않습니다 하지만 대문자로 쓰여집니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../mfc/class-library-overview.md)
