---
title: /CLRSUPPORTLASTERROR(PInvoke 호출의 마지막 오류 코드 유지)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: 5e4a5c86e53d74c8b704ee3780991d496fc1802a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807678"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR(PInvoke 호출의 마지막 오류 코드 유지)

**/CLRSUPPORTLASTERROR**기본적으로 켜져 있는, 사용 하 여 컴파일된 코드에서 DLL의 네이티브 함수를 호출할 수 있는 P/Invoke 메커니즘을 통해 함수의 마지막 오류 코드를 호출 하는 유지 **/clr**합니다.

## <a name="syntax"></a>구문

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>설명

마지막 오류 코드를 유지 하면서 성능 저하를 의미 합니다.  마지막 오류 코드를 유지 하면서 성능 저하를 유발 하지 않을 경우 연결할 **/CLRSUPPORTLASTERROR:NO**합니다.

사용 하 여 연결 하 여 성능에 미치는 영향을 최소화할 수 있습니다 **/CLRSUPPORTLASTERROR:SYSTEMDLL**만 시스템 Dll에서에서 함수에 대 한 마지막 오류 코드를 유지 합니다.  시스템 DLL은 다음 중 하나로 정의 됩니다.

|||||
|-|-|-|-|
|ACLUI 합니다. DLL|ACTIVEDS 합니다. DLL|ADPTIF 합니다. DLL|ADVAPI32.DLL|
|ASYCFILT.DLL|AUTHZ 합니다. DLL|AVICAP32.DLL|AVIFIL32.DLL|
|CABINET.DLL|CLUSAPI.DLL|COMCTL32.DLL|COMDLG32.DLL|
|COMSVCS.DLL|CREDUI 합니다. DLL|CRYPT32.DLL|CRYPTNET.DLL|
|CRYPTUI.DLL|D3D8THK.DLL|DBGENG.DLL|DBGHELP.DLL|
|DCIMAN32.DLL|DNSAPI.DLL|DSPROP.DLL|DSUIEXT 합니다. DLL|
|GDI32.DLL|GLU32.DLL|HLINK 합니다. DLL|ICM32.DLL|
|IMAGEHLP.DLL|IMM32.DLL|IPHLPAPI.DLL|IPROP.DLL|
|KERNEL32.DLL|KSUSER 합니다. DLL|LOADPERF 합니다. DLL|LZ32.DLL|
|MAPI32.DLL|MGMTAPI.DLL|MOBSYNC.DLL|MPR.DLL|
|MPRAPI.DLL|MQRT.DLL|MSACM32.DLL|MSCMS.DLL|
|MSI.DLL|MSIMG32.DLL|MSRATING 합니다. DLL|MSTASK.DLL|
|MSVFW32.DLL|MSWSOCK 합니다. DLL|MTXEX.DLL|NDDEAPI.DLL|
|NETAPI32.DLL|NPPTOOLS 합니다. DLL|NTDSAPI.DLL|NTDSBCLI.DLL|
|NTMSAPI.DLL|ODBC32.DLL|ODBCBCP.DLL|OLE32.DLL|
|OLEACC.DLL|OLEAUT32.DLL|OLEDLG.DLL|OPENGL32.DLL|
|PDH.DLL|POWRPROF.DLL|QOSNAME.DLL|쿼리입니다. DLL|
|RASAPI32.DLL|RASDLG.DLL|RASSAPI.DLL|RESUTILS 합니다. DLL|
|RICHED20 합니다. DLL|RPCNS4.DLL|RPCRT4.DLL|RTM.DLL|
|RTUTILS 합니다. DLL|SCARDDLG.DLL|SECUR32.DLL|SENSAPI 합니다. DLL|
|SETUPAPI.DLL|SFC.DLL|SHELL32.DLL|SHFOLDER 합니다. DLL|
|SHLWAPI.DLL|SISBKUP.DLL|SNMPAPI.DLL|SRCLIENT 합니다. DLL|
|STI.DLL|TAPI32.DLL|TRAFFIC.DLL|URL.DLL|
|URLMON 합니다. DLL|USER32.DLL|USERENV 합니다. DLL|USP10.DLL|
|UXTHEME.DLL|VDMDBG.DLL|버전. DLL|WINFAX 합니다. DLL|
|WINHTTP.DLL|WININET 합니다. DLL|WINMM.DLL|WINSCARD 합니다. DLL|
|WINTRUST.DLL|WLDAP32.DLL|WOW32.DLL|WS2_32.DLL|
|WSNMP32.DLL|WSOCK32.DLL|WTSAPI32.DLL|XOLEHLP.DLL|

> [!NOTE]
>  마지막 오류를 유지 하면서 동일한 모듈의 CLR 코드에서 사용 되는 관리 되지 않는 함수에 대 한 지원 되지 않습니다.

- 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md)을 참조하세요.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. 에 옵션을 입력 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="example"></a>예제

다음 샘플 마지막 오류를 수정 하는 하나의 내보낸된 함수를 사용 하 여 네이티브 DLL을 정의 합니다.

```
// CLRSUPPORTLASTERROR_dll.cpp
// compile with: /LD
#include <windows.h>
#include <math.h>

#pragma unmanaged
__declspec(dllexport) double MySqrt(__int64 n) {
   SetLastError(DWORD(-1));
   return sqrt(double(n));
}
```

## <a name="example"></a>예제

다음 샘플 사용 DLL을 사용 하는 방법을 보여주는 **/CLRSUPPORTLASTERROR**합니다.

```
// CLRSUPPORTLASTERROR_client.cpp
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll
// processor: x86
#include <windows.h>
#include <wininet.h>
#include <stdio.h>
#include <math.h>

#pragma comment(lib, "wininet.lib")

double MySqrt(__int64 n);

#pragma managed
int main() {
   double   d = 0.0;
   __int64 n = 65;
   HANDLE  hGroup = NULL;
   GROUPID groupID;
   DWORD   dwSet = 127, dwGet = 37;

   SetLastError(dwSet);
   d = MySqrt(n);
   dwGet = GetLastError();

   if (dwGet == DWORD(-1))
      printf_s("GetLastError for application call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for application call failed (%d).\n",
             dwGet);

   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,
                           0, 0, &groupID, 0);
   dwGet = GetLastError();
   if (dwGet == 183)
      printf_s("GetLastError for system call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for system call failed (%d).\n",
             dwGet);
}
```

```Output
GetLastError for application call failed (127).
GetLastError for system call succeeded (183).
```

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
