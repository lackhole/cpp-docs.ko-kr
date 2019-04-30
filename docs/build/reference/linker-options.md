---
title: MSVC 링커 옵션
ms.date: 08/20/2018
f1_keywords:
- link
helpviewer_keywords:
- linker [C++]
- linker [C++], options listed
- libraries [C++], linking to COFF
- LINK tool [C++], linker options
ms.assetid: c1d51b8a-bd23-416d-81e4-900e02b2c129
ms.openlocfilehash: 7ff8ecd6a607aac59fca6d32fa2784e7e3e4268f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301762"
---
# <a name="linker-options"></a>링커 옵션

LINK.exe는 COFF(Common Object File Format) 개체 파일과 라이브러리를 연결하여 실행 파일(.exe) 또는 DLL(동적 연결 라이브러리)을 만듭니다.

다음 테이블에는 LINK.exe의 옵션이 나열됩니다. LINK에 대한 자세한 내용은 다음을 참조하세요.

- [컴파일러 제어 LINK 옵션](compiler-controlled-link-options.md)

- [LINK 입력 파일](link-input-files.md)

- [LINK 출력](link-output.md)

- [예약어](reserved-words.md)

명령줄에서 링커 옵션은 대/소문자를 구분 합니다. 예를 들어 /base와 /BASE 동일한 작업을 의미 합니다. 명령줄 또는 Visual Studio에서 각 옵션을 지정하는 방법에 대한 자세한 내용은 해당 옵션에 대한 설명서를 참조하세요.

[주석](../../preprocessor/comment-c-cpp.md) pragma를 사용하여 일부 링커 옵션을 지정할 수 있습니다.

|옵션|용도|
|------------|-------------|
|[@](at-specify-a-linker-response-file.md)|지시 파일을 지정합니다.|
|[/ALIGN](align-section-alignment.md)|각 섹션의 맞춤을 지정합니다.|
|[/ALLOWBIND](allowbind-prevent-dll-binding.md)|DLL을 바인딩할 수 없도록 지정합니다.|
|[/ALLOWISOLATION](allowisolation-manifest-lookup.md)|매니페스트 조회 동작을 지정합니다.|
|[/APPCONTAINER](appcontainer-windows-store-app.md)|앱을 appcontainer 프로세스 환경 내에서 실행해야 하는지 여부를 지정합니다.|
|[/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)|관리되는 이미지에 <xref:System.Diagnostics.DebuggableAttribute> 를 추가합니다.|
|[/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)|관리되는 리소스에 대한 링크를 만듭니다.|
|[/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)|MSIL(Microsoft Intermediate Language) 모듈을 어셈블리로 가져와야 하는지 여부를 지정합니다.|
|[/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)|관리되는 리소스 파일을 어셈블리에 포함합니다.|
|[/BASE](base-base-address.md)|프로그램의 기준 주소를 설정합니다.|
|[/CGTHREADS](cgthreads-compiler-threads.md)|링크 타임 코드 생성을 지정할 때 최적화 및 코드 생성에 사용할 cl.exe 스레드 수를 설정합니다.|
|[/CLRIMAGETYPE](clrimagetype-specify-type-of-clr-image.md)|CLR 이미지의 형식(IJW, 순수 또는 안전)을 설정합니다.|
|[/CLRSUPPORTLASTERROR](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|P/Invoke 메커니즘을 통해 호출된 함수의 마지막 오류 코드를 유지합니다.|
|[/CLRTHREADATTRIBUTE](clrthreadattribute-set-clr-thread-attribute.md)|CLR 프로그램의 진입점에 적용할 스레딩 특성을 지정합니다.|
|[/CLRUNMANAGEDCODECHECK](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md)|링커가 SuppressUnmanagedCodeSecurity 특성을 관리 코드에서 네이티브 DLL로 호출하는 링커 생성 PInvoke 스텁에 적용할지 여부를 지정합니다.|
|[/DEBUG](debug-generate-debug-info.md)|디버깅 정보를 생성합니다.|
|[/DEBUGTYPE](debugtype-debug-info-options.md)|디버깅 정보에 포함할 데이터를 지정합니다.|
|[/DEF](def-specify-module-definition-file.md)|모듈 정의 파일(.def)을 링커에 전달합니다.|
|[/DEFAULTLIB](defaultlib-specify-default-library.md)|외부 참조가 확인되면 지정한 라이브러리를 검색합니다.|
|[/DELAY](delay-delay-load-import-settings.md)|DLL의 지연 로드를 제어합니다.|
|[/DELAYLOAD](delayload-delay-load-import.md)|지정한 DLL의 지연 로드를 일으킵니다.|
|[/DELAYSIGN](delaysign-partially-sign-an-assembly.md)|어셈블리에 부분적으로 서명합니다.|
|[/DEPENDENTLOADFLAG](dependentloadflag.md)|종속 DLL 로드에 기본 플래그를 설정합니다.|
|[/DLL](dll-build-a-dll.md)|DLL을 빌드합니다.|
|[/DRIVER](driver-windows-nt-kernel-mode-driver.md)|커널 모드 드라이버를 만듭니다.|
|[/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)|ASLR(Address Space Layout Randomization) 기능을 사용하여 로드할 때 무작위로 기준 주소를 다시 지정할 수 있는 실행 가능 이미지를 생성할지 여부를 지정합니다.|
|[/ENTRY](entry-entry-point-symbol.md)|시작 주소를 설정합니다.|
|[/errorReport](errorreport-report-internal-linker-errors.md)|Microsoft에 내부 링커 오류를 보고합니다.|
|[/EXPORT](export-exports-a-function.md)|함수를 내보냅니다.|
|[/FILEALIGN](filealign.md)|지정된 된 값의 배수에서 출력 파일 내의 섹션을 맞춥니다.|
|[/FIXED](fixed-fixed-base-address.md)|기본 설정 기준 주소에서만 로드할 수 있는 프로그램을 만듭니다.|
|[/FORCE](force-force-file-output.md)|확인되지 않은 기호 또는 두 번 이상 정의된 기호를 사용해도 링크가 강제로 완료되도록 합니다.|
|[/FUNCTIONPADMIN](functionpadmin-create-hotpatchable-image.md)|핫 패치할 수 있는 이미지를 만듭니다.|
|[/GENPROFILE, /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|이러한 두 옵션은 링커에서 PGO(프로필 기반 최적화)를 지원하기 위한 .pgd 파일의 생성을 지정합니다. /GENPROFILE 및 /FASTGENPROFILE은 서로 다른 기본 매개 변수를 사용합니다.|
|[/GUARD](guard-enable-guard-checks.md)|제어 흐름 가드 보호를 사용하도록 설정합니다.|
|[/HEAP](heap-set-heap-size.md)|힙 크기를 바이트 단위로 설정합니다.|
|[/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)|높은 엔트로피 64비트 ASLR(Address Space Layout Randomization)에 대한 지원을 지정합니다.|
|[/IDLOUT](idlout-name-midl-output-files.md)|.idl 파일과 기타 MIDL 출력 파일의 이름을 지정합니다.|
|[/IGNORE](ignore-ignore-specific-warnings.md)|지정된 링커 경고 출력을 표시하지 않습니다.|
|[/IGNOREIDL](ignoreidl-don-t-process-attributes-into-midl.md)|.idl 파일로의 특성 정보 처리를 방지합니다.|
|[/IMPLIB](implib-name-import-library.md)|기존 가져오기 라이브러리 이름을 재정의합니다.|
|[/INCLUDE](include-force-symbol-references.md)|기호 참조를 강제합니다.|
|[/INCREMENTAL](incremental-link-incrementally.md)|증분 링크를 제어합니다.|
|[/INTEGRITYCHECK](integritycheck-require-signature-check.md)|로드할 때 모듈에 서명 확인이 필요한지 지정합니다.|
|[/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)|어셈블리에 서명할 키 컨테이너를 지정합니다.|
|[/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|어셈블리에 서명할 키 또는 키 쌍을 지정합니다.|
|[/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)|컴파일러에 애플리케이션이 2GB를 넘는 주소를 지원한다고 알립니다.|
|[/LIBPATH](libpath-additional-libpath.md)|환경 라이브러리 경로 앞을 검색할 경로를 지정합니다.|
|[/LTCG](ltcg-link-time-code-generation.md)|링크 타임 코드 생성을 지정합니다.|
|[/MACHINE](machine-specify-target-platform.md)|대상 플랫폼을 지정합니다.|
|[/MANIFEST](manifest-create-side-by-side-assembly-manifest.md)|side-by-side 매니페스트 파일을 만들고 선택적으로 이진에 포함합니다.|
|[/MANIFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md)|지정 된 \<dependentAssembly > 매니페스트 파일의 섹션입니다.|
|[/MANIFESTFILE](manifestfile-name-manifest-file.md)|매니페스트 파일의 기본 이름을 변경합니다.|
|[/MANIFESTINPUT](manifestinput-specify-manifest-input.md)|처리할 링커의 매니페스트 입력 파일을 지정해서 이진에 포함합니다. 이 옵션을 여러 번 사용하여 매니페스트 입력 파일을 두 개 이상 지정합니다.|
|[/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md)|UAC(사용자 계정 컨트롤) 정보를 program 매니페스트에 포함할지 여부를 지정합니다.|
|[/MAP](map-generate-mapfile.md)|맵 파일을 만듭니다.|
|[/MAPINFO](mapinfo-include-information-in-mapfile.md)|맵 파일에 지정된 정보를 포함합니다.|
|[/MERGE](merge-combine-sections.md)|섹션을 결합합니다.|
|[/MIDL](midl-specify-midl-command-line-options.md)|MIDL 명령줄 옵션을 지정합니다.|
|[/NATVIS](natvis-add-natvis-to-pdb.md)|PDB에 Natvis 파일에서 디버거 시각화 도우미를 추가합니다.|
|[/NOASSEMBLY](noassembly-create-a-msil-module.md)|.NET Framework 어셈블리의 생성을 억제합니다.|
|[/NODEFAULTLIB](nodefaultlib-ignore-libraries.md)|외부 참조가 확인되면 모든 (또는 지정한) 기본 라이브러리를 무시합니다.|
|[/NOENTRY](noentry-no-entry-point.md)|리소스 전용 DLL을 만듭니다.|
|[/NOLOGO](nologo-suppress-startup-banner-linker.md)|시작 배너를 표시하지 않습니다.|
|[/NXCOMPAT](nxcompat-compatible-with-data-execution-prevention.md)|실행 파일이 Windows 데이터 실행 방지 기능과 호환되는지 확인했음을 표시합니다.|
|[/OPT](opt-optimizations.md)|LINK 최적화를 제어합니다.|
|[/ORDER](order-put-functions-in-order.md)|COMDAT를 미리 결정된 순서에 따라 이미지에 배치합니다.|
|[/OUT](out-output-file-name.md)|출력 파일 이름을 지정합니다.|
|[/PDB](pdb-use-program-database.md)|PDB(프로그램 데이터베이스) 파일을 만듭니다.|
|[/PDBALTPATH](pdbaltpath-use-alternate-pdb-path.md)|PDB 파일을 저장할 다른 위치를 사용합니다.|
|[/PDBSTRIPPED](pdbstripped-strip-private-symbols.md)|전용 기호가 없는 PDB(프로그램 데이터베이스) 파일을 만듭니다.|
|[/PGD](pgd-specify-database-for-profile-guided-optimizations.md)|프로필 기반 최적화에 필요한 .pgd 파일을 지정합니다.|
|[/POGOSAFEMODE](pogosafemode-linker-option.md)|**사용 되지 않는** 스레드로부터 안전한 PGO 계측 된 빌드를 만듭니다.|
|[/PROFILE](profile-performance-tools-profiler.md)|성능 도구 프로파일러와 함께 사용할 수 있는 출력 파일을 생성합니다.|
|[/RELEASE](release-set-the-checksum.md)|.exe 헤더의 체크섬을 설정합니다.|
|[/SAFESEH](safeseh-image-has-safe-exception-handlers.md)|이미지에 안전한 예외 처리기 테이블을 포함하도록 지정합니다.|
|[/SECTION](section-specify-section-attributes.md)|섹션의 특성을 재정의합니다.|
|[/SOURCELINK](sourcelink.md)|PDB에 추가할 SourceLink 파일을 지정 합니다.|
|[/STACK](stack-stack-allocations.md)|스택 크기를 바이트 단위로 설정합니다.|
|[/STUB](stub-ms-dos-stub-file-name.md)|MS-DOS 스텁 프로그램을 Win32 프로그램에 첨부합니다.|
|[/SUBSYSTEM](subsystem-specify-subsystem.md)|운영 체제에 .exe 파일을 실행하는 방법을 알립니다.|
|[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md)|스왑 파일을 실행하기 전에 스왑 파일에 링커 옵션을 복사하도록 운영 체제에 지시합니다.|
|[/TLBID](tlbid-specify-resource-id-for-typelib.md)|링커 생성 형식 라이브러리의 리소스 ID를 지정합니다.|
|[/TLBOUT](tlbout-name-dot-tlb-file.md)|.tlb 파일과 기타 MIDL 출력 파일의 이름을 지정합니다.|
|[/TSAWARE](tsaware-create-terminal-server-aware-application.md)|터미널 서버에서 실행되는 특별히 디자인된 애플리케이션을 만듭니다.|
|[/USEPROFILE](useprofile.md)|최적화 학습 데이터를 사용 하 여 프로필 기반 최적화 된 이미지를 만듭니다.|
|[/VERBOSE](verbose-print-progress-messages.md)|링커 진행 메시지를 출력합니다.|
|[/VERSION](version-version-information.md)|버전 번호를 할당합니다.|
|[/WHOLEARCHIVE](wholearchive-include-all-library-object-files.md)|지정 된 정적 라이브러리에서 모든 개체 파일을 포함합니다.|
|[/WINMD](winmd-generate-windows-metadata.md)|Windows 런타임 메타데이터 파일을 생성하도록 설정합니다.|
|[/WINMDFILE](winmdfile-specify-winmd-file.md)|[/WINMD](winmd-generate-windows-metadata.md) 링커 옵션으로 생성된 Windows 런타임 메타데이터(winmd) 출력 파일의 파일 이름을 지정합니다.|
|[/WINMDKEYFILE](winmdkeyfile-specify-winmd-key-file.md)|Windows 런타임 메타데이터 파일에 서명할 키 또는 키 쌍을 지정합니다.|
|[/WINMDKEYCONTAINER](winmdkeycontainer-specify-key-container.md)|Windows 메타데이터 파일에 서명할 키 컨테이너를 지정합니다.|
|[/WINMDDELAYSIGN](winmddelaysign-partially-sign-a-winmd.md)|winmd 파일에 공개 키를 배치하여 Windows 런타임 메타데이터 파일(.winmd)에 부분적으로 서명합니다.|
|[/WX](wx-treat-linker-warnings-as-errors.md)|링커 경고를 오류로 처리합니다.|

자세한 내용은 [Compiler-Controlled LINK Options](compiler-controlled-link-options.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](c-cpp-building-reference.md)<br/>
[MSVC 링커 참조](linking.md)
