---
title: 기존 ActiveX 컨트롤 업그레이드
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX controls [MFC], Internet
- LPK files for Internet controls
- safe for scripting and initialization (controls)
- OLE controls [MFC], upgrading to ActiveX
- CAB files, for ActiveX controls
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], packaging code for download
- upgrading ActiveX controls
- licensing ActiveX controls
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
ms.openlocfilehash: 22cbeaa5ac0f92e2b7bcc9dcbd06df9ab4ccaff5
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503830"
---
# <a name="upgrading-an-existing-activex-control"></a>기존 ActiveX 컨트롤 업그레이드

기존 ActiveX 컨트롤 (이전의 OLE 컨트롤) 수정 하지 않고 인터넷에서 사용할 수 있습니다. 그러나 다음 성능 향상을 위해 컨트롤을 수정 하는 것이 좋습니다.

> [!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

웹 페이지에 컨트롤을 사용할 경우 추가 고려 사항이 있습니다. .Ocx 파일 및 모든 지원 파일 대상 컴퓨터에 있어야 또는 인터넷을 통해 다운로드할 수 있습니다. 이렇게 하면 코드 크기와 다운로드 시간이 중요 한 고려 합니다. 서명 된.cab 파일의 다운로드를 패키지할 수 있습니다. 스크립트 및 초기화에 안전으로 컨트롤을 표시할 수 있습니다.

이 문서에서는 다음 토픽을 설명합니다.

- [다운로드 패키징 코드](#_core_packaging_code_for_downloading)

- [스크립팅 및 초기화에 대 한 안전한 컨트롤 표시](#_core_marking_a_control_safe_for_scripting_and_initializing)

- [라이선스 문제](#_core_licensing_issues)

- [코드 서명](#_core_signing_code)

- [색상표를 관리합니다.](#_core_managing_the_palette)

- [Internet Explorer 브라우저 보안 수준 및 동작을 제어](#_core_internet_explorer_browser_safety_levels_and_control_behavior)

에 설명 된 대로 최적화를 추가할 수도 있습니다 [ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)합니다. 모니커를 사용 하 여 속성을 다운로드할 수 있습니다 및 대형 Blob을 비동기적으로에 설명 된 대로 [인터넷의 ActiveX 컨트롤](../mfc/activex-controls-on-the-internet.md)합니다.

##  <a name="_core_packaging_code_for_downloading"></a> 다운로드 패키징 코드

이 주제에 대 한 자세한 내용은 참조 하세요. [패키징 ActiveX 컨트롤](https://docs.microsoft.com//previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa751974%28v%3dvs.85%29)합니다.

### <a name="the-codebase-tag"></a>코드 베이스 태그

ActiveX 컨트롤 사용 하 여 웹 페이지에 포함 된를 `<OBJECT>` 태그입니다. 합니다 `CODEBASE` 의 매개 변수는 `<OBJECT>` 태그에서 컨트롤을 다운로드 하는 위치를 지정 합니다. `CODEBASE` 가리킬 수 많은 다른 파일 형식은 성공적으로 합니다.

### <a name="using-the-codebase-tag-with-an-ocx-file"></a>코드 베이스 태그를 사용 하 여 OCX 파일

```
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"
```

이 솔루션만 컨트롤의.ocx 파일을 다운로드 하며 클라이언트 컴퓨터에 이미 설치 되어 Dll을 모두 지원 합니다. 이 시각적 개체를 사용 하 여 작성 하는 Internet Explorer 및 MFC ActiveX 컨트롤에 대 한 작동 C++시각적 개체에 대 한 지원 Dll을 사용 하 여 Internet Explorer를 제공 하기 때문에, C++ 컨트롤입니다. Activex 컨트롤을 사용할 수 있는 다른 인터넷 브라우저를이 컨트롤을 보려면 사용 하는 경우에이 솔루션이 작동 하지 않습니다.

### <a name="using-the-codebase-tag-with-an-inf-file"></a>INF 파일을 사용 하 여 코드 베이스 태그를 사용 하 여

```
CODEBASE="http://example.microsoft.com/trustme.inf"
```

.Inf 파일.ocx와 해당 지원 파일 설치를 제어 됩니다. .Inf 파일에 서명 하는 것이 불가능 하기 때문에이 방법은 권장 되지 않습니다 (참조 [코드 서명](#_core_signing_code) 코드 서명에 대 한 포인터에 대 한).

### <a name="using-the-codebase-tag-with-a-cab-file"></a>CAB 파일을 사용 하 여 코드 베이스 태그를 사용 하 여

```
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"
```

캐비닛 파일은 MFC를 사용 하는 패키지 ActiveX 컨트롤에 권장 되는 방법입니다. 캐비닛 파일에 MFC ActiveX 컨트롤을 패키징.inf 파일을 ActiveX 컨트롤 및 모든 종속 Dll (예: MFC Dll)의 컨트롤 설치에 포함 될 수 있습니다. CAB 파일을 자동으로 사용 하는 빠른 다운로드에 대 한 코드를 압축 합니다. .Cab 파일에 대 한 구성 요소 다운로드를 사용 하는 경우 각 개별 구성 요소 보다 전체.cab 파일에 서명 하는 것이 더 빠릅니다.

### <a name="creating-cab-files"></a>CAB 파일 만들기

캐비닛 파일을 만들기 위한 도구를 지금의 일부인 합니다 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)합니다.

캐비닛 파일에서 가리키는 `CODEBASE` ActiveX 컨트롤에 대 한.ocx 파일 및 해당 설치를 제어 하는.inf 파일을 포함 해야 합니다. 사용자 컨트롤 파일의 이름을 지정 하 여 캐비닛 파일 및.inf 파일을 만듭니다. 이 캐비닛 파일 시스템에 이미 있을 수 있는 종속 Dll을 포함 하지 않습니다. 예를 들어, MFC Dll 별도 캐비닛 파일에 패키지 되 고 제어.inf 파일에서 참조 합니다.

CAB 파일을 만드는 방법에 대 한 세부 정보를 참조 하세요 [CAB 파일을 만드는](/windows/desktop/devnotes/cabinet-api-functions)합니다.

### <a name="the-inf-file"></a>INF 파일

다음 예제에서는, spindial.inf, 목록 버전 정보와 지원 파일이 필요한 MFC Spindial 제어 됩니다. MFC Dll의 위치는 Microsoft 웹 사이트에서 확인할 수 있습니다. mfc42.cab 제공 되 고 Microsoft에서 서명 됩니다.

```
Contents of spindial.inf:
[mfc42installer]
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab
[Olepro32.dll] - FileVersion=5,
    0,
    4261,
    0
[Mfc42.dll] - FileVersion=6,
    0,
    8168,
    0
[Msvcrt.dll] - FileVersion=6,
    0,
    8168,
    0
```

### <a name="the-object-tag"></a>\<개체 > 태그

다음 예제를 사용 하는 `<OBJECT>` MFC Spindial 샘플 컨트롤을 패키지 하는 태그입니다.

```
<OBJECT ID="Spindial1" WIDTH=100 HEIGHT=51
    CLASSID="CLSID:06889605-B8D0-101A-91F1-00608CEAD5B3"
    CODEBASE="http://example.microsoft.com/spindial.cab#Version=1,0,0,001">
<PARAM NAME="_Version" VALUE="65536">
<PARAM NAME="_ExtentX" VALUE="2646">
<PARAM NAME="_ExtentY" VALUE="1323">
<PARAM NAME="_StockProps" VALUE="0">
<PARAM NAME="NeedlePosition" VALUE="2">
</OBJECT>
```

이 경우 두 개의 파일과 spindial.ocx spindial.inf spindial.cab 포함 됩니다. 다음 명령을 캐비닛 파일을 빌드합니다.

```
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf
```

`-s 6144` 코드 서명에 캐비닛에 공간을 예약 하는 매개 변수입니다.

### <a name="the-version-tag"></a>버전 태그

`#Version` CAB 파일을 사용 하 여 지정 된 정보로 지정 된 컨트롤에 적용 됩니다 합니다 *CLASSID* 의 매개 변수는 `<OBJECT>` 태그입니다.

지정 된 버전에 따라 컨트롤을 다운로드를 할 수 있습니다. 전체 사양에 대 한는 `OBJECT` 태그를 포함 하는 *코드 베이스* 매개 변수, 참조 W3C입니다.

##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a> 스크립팅 및 초기화에 대 한 안전한 컨트롤 표시

웹 페이지에서 사용 하는 ActiveX 컨트롤 스크립트에 대 한 안전 하 고 실제로 안전 하지 않은 경우 초기화에 안전으로 표시 되어야 합니다. 안전 컨트롤을 디스크 IO를 수행 되거나 컴퓨터의 등록을 메모리에 직접 액세스 되지 않습니다.

스크립트에 대 한 안전 하 고 레지스트리를 통해 초기화에 안전으로 컨트롤을 표시할 수 있습니다. 수정 `DllRegisterServer` 스크립팅 및 레지스트리에 대 한 지 속성에 대 한 안전 하 게 컨트롤을 표시 하려면 다음과 유사한 항목을 추가 합니다. 대체 메서드를 구현 하는 것 `IObjectSafety`입니다.

스크립트 사용 및 지 속성에 대 한 안전 하 게 표시할 컨트롤에 대 한 Guid (Globally Unique Identifier)를 정의 합니다. 안전 하 게 스크립팅할 수 있는 컨트롤은 다음과 유사한 레지스트리 항목을 포함 합니다.

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
```

영구 데이터를 안전 하 게 초기화할 수 있는 컨트롤은 유사한 레지스트리 항목을 사용 하 여 지 속성에 대 한 안전 하 게 표시 됩니다.

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

다음과 비슷한 항목을 추가 (대체 컨트롤의 클래스 ID 대신 `{06889605-B8D0-101A-91F1-00608CEAD5B3}`) 클래스 ID를 사용 하 여 키를 연결 하려면:

```
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

##  <a name="_core_licensing_issues"></a> 라이선스 문제

웹 페이지의 사용이 허가 된 컨트롤을 사용 하려는 경우 사용권 계약을 인터넷에서 사용할 수 있습니다 하에 대 한 라이선스 패키지 파일 (LPK) 만들기를 확인 해야 합니다.

Internet Explorer를 실행 하는 컴퓨터 컨트롤을 사용 하도록 라이선스가 없는 경우 사용이 허가 된 ActiveX 컨트롤을 HTML 페이지에서 제대로 로드 되지 않습니다. 예를 들어 사용이 허가 된 컨트롤을 시각적 개체를 사용 하 여 빌드된 C++, 여기서 컨트롤 작성 된 있지만 라이선스 정보가 포함 되지 않는 한 다른 컴퓨터에서 로드 되지 것입니다 컴퓨터 컨트롤을 사용 하 여 HTML 페이지를 올바르게 로드 됩니다.

Internet Explorer에서 사용이 허가 된 ActiveX 컨트롤을 사용 하려면 컨트롤에 대 한 라이선스 수 있는지 확인 하려면 공급 업체의 사용권 계약을 확인 해야 합니다.

- 재배포

- 인터넷에 있는 컨트롤의 사용

- 코드 베이스 매개 변수를 사용

라이센스가 없는 컴퓨터에서 HTML 페이지에 사용이 허가 된 컨트롤을 사용 하려면 라이선스 패키지 파일 (LPK)을 생성 해야 합니다. LPK 파일 HTML 페이지의 사용이 허가 된 컨트롤에 대 한 런타임 라이선스를 포함 합니다. 이 파일은 LPK_TOOL 통해 생성 됩니다. ActiveX SDK와 함께 제공 되는 EXE 수 있습니다.

#### <a name="to-create-an-lpk-file"></a>LPK 파일을 만들려면

1. LPK_TOOL를 실행 합니다. 컨트롤을 사용 하는 사용이 허가 된 컴퓨터에서 EXE 수 있습니다.

1. 에 **라이선스 패키지 Authoring Tool** 대화 상자의 합니다 **사용할 수 있는 컨트롤** 목록 상자에서 각 선택 페이지의 HTML 사용 하 고 클릭 하는 ActiveX 컨트롤 라이선스 **추가**.

1. 클릭 **저장 및 종료** LPK 파일에 대 한 이름을 입력 합니다. 이 LPK 파일을 만들고 응용 프로그램을 닫습니다.

#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>HTML 페이지의 사용이 허가 된 컨트롤을 포함 시키려면

1. HTML 페이지를 편집 합니다. HTML 페이지에서 삽입 하는 \<개체 > 전에 다른 라이선스 관리자 개체에 대 한 태그 \<개체 > 태그입니다. 라이선스 관리자는 Internet Explorer를 사용 하 여 설치 된 ActiveX 컨트롤입니다. 컨트롤의 클래스 ID는 다음과 같습니다. 라이선스 관리자 개체의 LPKPath 속성 LPK 파일의 이름과 경로를 설정 합니다. HTML 페이지 별로 LPK 파일 하나만 있을 수 있습니다.

```
<OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">
</OBJECT>
```

1. 삽입 된 \<개체 > 라이선스 관리자는 태그 뒤에 사용이 허가 된 컨트롤의 태그입니다.

   예를 들어 Microsoft 마스킹된 편집 컨트롤을 표시 하는 HTML 페이지는 다음과 같습니다. 라이선스 관리자 컨트롤에 대 한 ID가 첫 번째 클래스, 마스킹된 편집 컨트롤에 대 한 ID가 두 번째 클래스입니다. 이전에 만든 제작 파일의 상대 경로를 가리키도록 태그를 변경 하 고 컨트롤의 클래스 ID를 포함 하는 개체 태그를 추가 합니다.

1. 삽입 된 \<EMBED > NCompass ActiveX 플러그 인을 사용 하는 경우 LPK 파일의 특성입니다.

   활성 지원 브라우저에서 다른 컨트롤을 볼 수 있는 경우-NCompass ActiveX 플러그 인을 사용 하 여 Netscape 예를 들어-추가 해야 합니다는 \<EMBED > 아래와 같이 구문입니다.

```
<OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="maskedit.lpk">

<EMBED SRC = "maskedit.LPK">

</OBJECT>
<OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>
</OBJECT>
```

컨트롤 라이선스에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤: ActiveX 컨트롤 라이선스](../mfc/mfc-activex-controls-licensing-an-activex-control.md)합니다.

##  <a name="_core_signing_code"></a> 코드 서명

코드의 원본을 확인은 코드 서명 및 서명 된 이후 코드는 변경 되지 않았는지를 보장 하기 위해. 브라우저 보안 설정에 따라 사용자 코드를 다운로드 하기 전에 경고가 표시 될 수 있습니다. 사용자는 특정 인증서 소유자 또는 회사에 있는 경우 코드 서명 된 신뢰할 수 있는 경고 없이 다운로드 됩니다 신뢰 하도록 선택할 수 있습니다. 코드는 변조를 방지 하려면 디지털로 서명 됩니다.

최종 코드는 신뢰 경고 메시지를 표시 하지 않고 컨트롤을 자동으로 다운로드할 수 있도록 서명 되어 있는지 확인 합니다. 코드 서명 하는 방법에 대 한 내용은 Authenticode ActiveX SDK에 대 한 설명서를 확인 하 고 참조 [CAB 파일에 서명](/windows/desktop/devnotes/cabinet-api-functions)합니다.

트러스트 및 브라우저 보안 수준 설정에 따라 인증서를 서명 하는 개인 또는 회사를 식별 하 표시 될 수 있습니다. 보안 수준이 none, 또는 서명 된 컨트롤의 인증서 소유자를 신뢰 하는 경우 인증서 표시 되지 않습니다. 참조 [Internet Explorer 브라우저 보안 수준 및 동작을 제어](#_core_internet_explorer_browser_safety_levels_and_control_behavior) 컨트롤이 다운로드 되는 여부 및 표시 된 인증서 브라우저 보안 설정 결정 하는 방법에 대 한 내용은 합니다.

디지털 서명 보장 코드 서명 된 이후 변경 되지 않았습니다. 해시 코드를 가져오며 인증서에 포함 됩니다. 이 해시는 해시 코드를 다운로드 후 하지만 실행 하기 전에 수행 하는 코드를 사용 하 여 나중에 비교 됩니다. Verisign과 같은 회사 코드에 서명 하는 데 필요한 개인 및 공용 키를 제공할 수 있습니다. ActiveX SDK는 MakeCert를 테스트 인증서 만들기에 대 한 유틸리티를 사용 하 여 제공 됩니다.

##  <a name="_core_managing_the_palette"></a> 색상표를 관리합니다.

컨테이너는 색상표를 확인 하 고 앰비언트 속성으로 사용할 수 있도록 **DISPID_AMBIENT_PALETTE**합니다. 컨테이너 (예를 들어, Internet Explorer) 페이지에서 모든 ActiveX 컨트롤에서 자신의 색상표를 결정 하는 데 사용 되는 색상표를 선택 합니다. 이 디스플레이 깜박임을 방지 하 고 일관 된 모양을 제공 합니다.

컨트롤을 재정의할 수 `OnAmbientPropertyChange` 색상표 변경 알림을 처리할 수 있습니다.

컨트롤을 재정의할 수 `OnGetColorSet` 색 색상표를 그릴 집합을 반환 합니다. 컨테이너는 컨트롤 팔레트에서 인식 되었는지 확인 하려면 반환 값을 사용 합니다.

OCX 96 지침에 따르면 컨트롤 항상 백그라운드에서 팔레트가 깨 달아야 합니다.

앰비언트 palette 속성을 사용 하지 않는 오래 된 컨테이너는 WM_QUERYNEWPALETTE 및 WM_PALETTECHANGED 메시지를 보냅니다. 컨트롤을 재정의할 수 있습니다 `OnQueryNewPalette` 고 `OnPaletteChanged` 이러한 메시지를 처리할 수 있습니다.

##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a> Internet Explorer 브라우저 보안 수준 및 동작을 제어

브라우저에 사용자가 구성 가능한 보안 수준에 대 한 옵션이 있습니다. 웹 페이지에서 사용자의 컴퓨터를 손상 시킬 수 있는 현재 콘텐츠를 포함할 수 있으므로 브라우저 보안 수준에 대 한 옵션을 선택 하 여 사용자를 허용 합니다. 브라우저 보안 수준을 구현 방식에 따라 컨트롤을 전혀 다운로드 되지 또는 인증서 또는 사용자가 런타임에 컨트롤 다운로드할 것인지 여부를 선택할 수 있도록 경고 메시지가 표시 됩니다. 높음, 보통 및 낮은 보안 수준에서 Internet Explorer에서 ActiveX 컨트롤의 동작을 아래에 나열 됩니다.

### <a name="high-safety-mode"></a>보호 우선 모드

- 서명 되지 않은 컨트롤 다운로드 되지 않습니다.

- 신뢰할 수 없는 경우 서명 된 컨트롤을 인증서가 표시 됩니다 (사용자는 지금부터이 인증서 소유자의 코드를 항상 신뢰할 수 있는 옵션이 선택 가능).

- 안전한 것으로 표시 하는 컨트롤만 영구 데이터 및 스크립팅할 수 있습니다.

### <a name="medium-safety-mode"></a>보통 보안 모드

- 서명 되지 않은 컨트롤을 다운로드 하기 전에 경고가 표시 됩니다.

- 신뢰할 수 없는 경우 서명 된 컨트롤을 인증서가 표시 됩니다.

- 안전한 것으로 표시 되지 않은 컨트롤에는 경고가 표시 됩니다.

### <a name="low-safety-mode"></a>낮은 보안 모드

- 경고 없이 컨트롤을 다운로드 합니다.

- 스크립팅 및 지 속성에는 경고 없이 발생합니다.

## <a name="see-also"></a>참고자료

[MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)<br/>
[MFC ActiveX 컨트롤: ActiveX 컨트롤 라이선스 획득](../mfc/mfc-activex-controls-licensing-an-activex-control.md)
