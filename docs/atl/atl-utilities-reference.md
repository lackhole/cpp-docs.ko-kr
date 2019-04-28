---
title: ATL 유틸리티 참조
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: b5365ddc2924955fbdcf694065c4d4041a38eb01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62251865"
---
# <a name="atl-utilities-reference"></a>ATL 유틸리티 참조

형식의 경로 및 Url을 조작 하기 위한 코드를 제공 하는 ATL [CPathT](../atl/reference/cpatht-class.md) 하 고 [CUrl](../atl/reference/curl-class.md)합니다. 스레드 풀 [CThreadPool](../atl/reference/cthreadpool-class.md), 응용 프로그램에서 사용할 수 있습니다. 이 코드는 atlpath.h 및 atlutil.h에서 찾을 수 있습니다. 

### <a name="classes"></a>클래스

|||
|-|-|
|[CPathT 클래스](../atl/reference/cpatht-class.md)|이 클래스는 경로 나타냅니다.|
|[CDebugReportHook 클래스](../atl/reference/cdebugreporthook-class.md)|이 클래스를 사용 하 여 명명 된 파이프 디버그 보고서를 보내도록 합니다.|
|[CNonStatelessWorker 클래스](../atl/reference/cnonstatelessworker-class.md)|스레드 풀에서 요청을 받고 각 요청에 대해 생성 되 고 제거 하는 작업자 개체에 전달 합니다.|
|[CNoWorkerThread 클래스](../atl/reference/cnoworkerthread-class.md)|이 클래스에 대 한 인수로 사용 된 `MonitorClass` 동적 캐시 유지 관리를 사용 하지 않도록 설정 하려는 경우에 캐시 클래스 템플릿 매개 변수입니다.|
|[CThreadPool 클래스](../atl/reference/cthreadpool-class.md)|이 클래스는 작업 항목의 큐를 처리 하는 작업자 스레드 풀을 제공 합니다.|
|[CUrl 클래스](../atl/reference/curl-class.md)|이 클래스는 URL을 나타냅니다. 기존 URL을 구문 분석 하는지 여부를 다른 독립적으로 URL의 각 요소를 조작할 수 있습니다 문자열 또는 문자열 처음부터 작성 합니다.|
|[CWorkerThread 클래스](../atl/reference/cworkerthread-class.md)|이 클래스 작업자 스레드를 만듭니다 또는 기존 항목을 사용 하 여, 하나 이상의 커널 개체 핸들에서 대기 및 핸들 중 하나에 신호가 전달 될 때 지정 된 클라이언트 함수를 실행 합니다.|

### <a name="typedefs"></a>형식 정의

|||
|-|-|
|[CPath](../atl/reference/atl-typedefs.md#cpath)|특수화 [CPathT](../atl/reference/cpatht-class.md) 사용 하 여 `CString`입니다.|
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|특수화 [CPathT](../atl/reference/cpatht-class.md) 사용 하 여 `CStringA`입니다.|
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|특수화 [CPathT](../atl/reference/cpatht-class.md) 사용 하 여 `CStringW`입니다.|
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|사용 된 유형을 [CUrl](../atl/reference/curl-class.md) 포트 번호를 지정 합니다.|

### <a name="enums"></a>열거형

|||
|-|-|
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|이 열거형의 멤버에서 인식 하는 스키마에 대 한 상수를 제공 [CUrl](../atl/reference/curl-class.md)합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|안전하지 않은 문자와 공백을 이스케이프 시퀀스로 변환하는 등 URL을 정식화하려면 이 함수를 호출합니다.|
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|기본 URL과 상대 URL을 단일 정규 URL로 결합하려면 이 함수를 호출합니다.|
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|모든 안전하지 않은 문자를 이스케이프 시퀀스로 변환하려면 이 함수를 호출합니다.|
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|특정 인터넷 프로토콜 또는 체계를 사용 하 여 연결 된 기본 포트 번호를 가져오려면이 함수를 호출 합니다.|
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|16진수의 숫자 값을 가져오려면 이 함수를 호출합니다.|
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|URL에서 문자를 안전하게 사용할 수 있는지 확인하려면 이 함수를 호출합니다.|
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|이스케이프된 문자를 원래 값으로 다시 변환하려면 이 함수를 호출합니다.|
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|시스템 시간을 HTTP 헤더에서 사용하기에 적합한 형식의 문자열로 변환하려면 이 함수를 호출합니다.|

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha
)입니다. | |[ ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona)입니다. | |[ ATLPath::Append](../atl/reference/atl-path-functions.md#append)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda)입니다. | |[ ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota)입니다. | |[ ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea)입니다. | |[ ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea)입니다. | |[ ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa)입니다. | |[ ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha)입니다. | |[ ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa)입니다. | |[ ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa)입니다. | |[ ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona)입니다. | |[ ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea)입니다. | |[ ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera)입니다. | |[ ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya)입니다. | |[ ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca)입니다. | |[ ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa)입니다. | |[ ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea)입니다. | |[ ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota)입니다. | |[ ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota)입니다. | |[ ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca)입니다. | |[ ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| 이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera)입니다. | |[ ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| 이 함수는에 대 한 오버 로드 된 래퍼를 [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).| |[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)|This function is an overloaded wrapper for [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).| |[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)|This function is an overloaded wrapper for [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).| |[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)|This function is an overloaded wrapper for [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).| |[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)|This function is an overloaded wrapper for [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).| |[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)|This function is an overloaded wrapper for [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).| |[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)|This function is an overloaded wrapper for [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).| |[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)|This function is an overloaded wrapper for [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).| |[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)|This function is an overloaded wrapper for [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).| |[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)|This function is an overloaded wrapper for [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).| |[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)|This function is an overloaded wrapper for [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).| |[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)|This function is an overloaded wrapper for [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).| |[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)|This function is an overloaded wrapper for [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).| |[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)|This function is an overloaded wrapper for [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).| |[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)|This function is an overloaded wrapper for [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).|

## <a name="see-also"></a>참고자료

[개념](../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM 데스크톱 구성 요소](../atl/atl-com-desktop-components.md)
