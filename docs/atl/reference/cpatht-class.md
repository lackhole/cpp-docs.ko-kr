---
title: CPathT 클래스
ms.date: 03/27/2019
f1_keywords:
- CPathT
- ATLPATH/ATL::CPathT
- ATLPATH/ATL::CPathT::PCXSTR
- ATLPATH/ATL::CPathT::PXSTR
- ATLPATH/ATL::CPathT::XCHAR
- ATLPATH/ATL::CPathT::CPathT
- ATLPATH/ATL::CPathT::AddBackslash
- ATLPATH/ATL::CPathT::AddExtension
- ATLPATH/ATL::CPathT::Append
- ATLPATH/ATL::CPathT::BuildRoot
- ATLPATH/ATL::CPathT::Canonicalize
- ATLPATH/ATL::CPathT::Combine
- ATLPATH/ATL::CPathT::CommonPrefix
- ATLPATH/ATL::CPathT::CompactPath
- ATLPATH/ATL::CPathT::CompactPathEx
- ATLPATH/ATL::CPathT::FileExists
- ATLPATH/ATL::CPathT::FindExtension
- ATLPATH/ATL::CPathT::FindFileName
- ATLPATH/ATL::CPathT::GetDriveNumber
- ATLPATH/ATL::CPathT::GetExtension
- ATLPATH/ATL::CPathT::IsDirectory
- ATLPATH/ATL::CPathT::IsFileSpec
- ATLPATH/ATL::CPathT::IsPrefix
- ATLPATH/ATL::CPathT::IsRelative
- ATLPATH/ATL::CPathT::IsRoot
- ATLPATH/ATL::CPathT::IsSameRoot
- ATLPATH/ATL::CPathT::IsUNC
- ATLPATH/ATL::CPathT::IsUNCServer
- ATLPATH/ATL::CPathT::IsUNCServerShare
- ATLPATH/ATL::CPathT::MakePretty
- ATLPATH/ATL::CPathT::MatchSpec
- ATLPATH/ATL::CPathT::QuoteSpaces
- ATLPATH/ATL::CPathT::RelativePathTo
- ATLPATH/ATL::CPathT::RemoveArgs
- ATLPATH/ATL::CPathT::RemoveBackslash
- ATLPATH/ATL::CPathT::RemoveBlanks
- ATLPATH/ATL::CPathT::RemoveExtension
- ATLPATH/ATL::CPathT::RemoveFileSpec
- ATLPATH/ATL::CPathT::RenameExtension
- ATLPATH/ATL::CPathT::SkipRoot
- ATLPATH/ATL::CPathT::StripPath
- ATLPATH/ATL::CPathT::StripToRoot
- ATLPATH/ATL::CPathT::UnquoteSpaces
- ATLPATH/ATL::CPathT::m_strPath
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
ms.openlocfilehash: 109f9baefd0e6775db05eeba8cb78542bf60a9ac
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565794"
---
# <a name="cpatht-class"></a>CPathT 클래스

이 클래스는 경로 나타냅니다.

> [!IMPORTANT]
> 이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>매개 변수

*StringType*<br/>
경로 대해 사용 하는 ATL/MFC 문자열 클래스 (참조 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)).

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CPathT::PCXSTR](#pcxstr)|상수 문자열 형식입니다.|
|[CPathT::PXSTR](#pxstr)|문자열 형식입니다.|
|[CPathT::XCHAR](#xchar)|문자 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPathT::CPathT](#cpatht)|경로 대 한 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPathT::AddBackslash](#addbackslash)|경로 대 한 올바른 구문을 만들려면 문자열의 끝에 백슬래시를 추가 하려면이 메서드를 호출 합니다.|
|[CPathT::AddExtension](#addextension)|경로에 파일 확장명을 추가 하려면이 메서드를 호출 합니다.|
|[CPathT::Append](#append)|현재 경로에 문자열을 추가 하려면이 메서드를 호출 합니다.|
|[CPathT::BuildRoot](#buildroot)|지정 된 드라이브에서 루트 경로 만들려면이 메서드를 호출 합니다.|
|[CPathT::Canonicalize](#canonicalize)|경로 정규 형식으로 변환 하려면이 메서드를 호출 합니다.|
|[CPathT::Combine](#combine)|디렉터리 이름을 나타내는 문자열 및 하나의 경로에 파일 경로 이름을 나타내는 문자열을 연결 하려면이 메서드를 호출 합니다.|
|[CPathT::CommonPrefix](#commonprefix)|지정된 된 경로 현재 경로 사용 하 여 공통 접두사를 공유 하는지 여부를 확인 하려면이 메서드를 호출 합니다.|
|[CPathT::CompactPath](#compactpath)|줄임표를 사용 하 여 경로 구성 요소를 대체 하 여 지정 된 픽셀 너비 안에 맞도록 파일 경로 자를이 메서드를 호출 합니다.|
|[CPathT::CompactPathEx](#compactpathex)|줄임표를 사용 하 여 경로 구성 요소를 대체 하 여 지정된 된 문자 수 내에 맞게 파일 경로 자를이 메서드를 호출 합니다.|
|[CPathT::FileExists](#fileexists)|이 경로 이름에 파일이 있는지 여부를 확인 하려면이 메서드를 호출 합니다.|
|[CPathT::FindExtension](#findextension)|경로 내에서 파일 확장명의 위치를 찾으려면이 메서드를 호출 합니다.|
|[CPathT::FindFileName](#findfilename)|경로 내에서 파일 이름과 위치를 찾으려면이 메서드를 호출 합니다.|
|[CPathT::GetDriveNumber](#getdrivenumber)|'A'-'Z' 범위에서 드라이브 문자에 대 한 경로 검색 하 고 해당 드라이브 수를 반환 하려면이 메서드를 호출 합니다.|
|[CPathT::GetExtension](#getextension)|경로에서 파일 확장명을 가져오려면이 메서드를 호출 합니다.|
|[CPathT::IsDirectory](#isdirectory)|경로가 올바른 디렉터리 위치에 있는지 여부를 확인 하려면이 메서드를 호출 합니다.|
|[CPathT::IsFileSpec](#isfilespec)|모든 경로 구분 문자에 대 한 경로 검색 하려면이 메서드를 호출 (예를 들어, ':' 또는 '\\'). 경로 구분 문자가 있는 경우 경로 파일 사양 경로일으로 간주 됩니다.|
|[CPathT::IsPrefix](#isprefix)|전달 된 형식의 올바른 접두사를 경로 포함 되는지 여부를 확인 하려면이 메서드를 호출 *pszPrefix*합니다.|
|[CPathT::IsRelative](#isrelative)|상대 경로 인지 확인 하려면이 메서드를 호출 합니다.|
|[CPathT::IsRoot](#isroot)|경로 디렉터리 루트 인지 확인 하려면이 메서드를 호출 합니다.|
|[CPathT::IsSameRoot](#issameroot)|다른 경로 현재 경로 사용 하 여 공통 루트 구성 요소에 있는지 여부를 확인 하려면이 메서드를 호출 합니다.|
|[CPathT::IsUNC](#isunc)|경로 서버에 대 한 유효한 UNC (범용 명명 규칙) 경로 인지 여부를 확인 하려면이 메서드를 호출 하 고 공유 합니다.|
|[CPathT::IsUNCServer](#isuncserver)|경로만 서버에 대 한 유효한 UNC (범용 명명 규칙) 경로 인지 여부를 확인 하려면이 메서드를 호출 합니다.|
|[CPathT::IsUNCServerShare](#isuncservershare)|올바른 UNC (범용 명명 규칙) 공유 경로 경로 인지 확인 하려면이 메서드를 호출 \\ \  *server*\ *공유*합니다.|
|[CPathT::MakePretty](#makepretty)|경로 경로 일관 된 모양을 제공 하는 모든 소문자를 변환 하려면이 메서드를 호출 합니다.|
|[CPathT::MatchSpec](#matchspec)|와일드 카드 일치 유형을 포함 하는 문자열에 대 한 경로 검색 하려면이 메서드를 호출 합니다.|
|[CPathT::QuoteSpaces](#quotespaces)|이 메서드는 공백을 포함 하는 경우 경로를 따옴표로 묶습니다를 호출 합니다.|
|[CPathT::RelativePathTo](#relativepathto)|다른 하나의 파일 또는 폴더에서 상대 경로 만들려면이 메서드를 호출 합니다.|
|[CPathT::RemoveArgs](#removeargs)|경로에서 명령줄 인수를 제거 하려면이 메서드를 호출 합니다.|
|[CPathT::RemoveBackslash](#removebackslash)|경로 후행 백슬래시를 제거 하려면이 메서드를 호출 합니다.|
|[CPathT::RemoveBlanks](#removeblanks)|경로에서 모든 선행 및 후행 공백을 제거 하려면이 메서드를 호출 합니다.|
|[CPathT::RemoveExtension](#removeextension)|있는 경우 경로에서 파일 확장명을 제거 하려면이 메서드를 호출 합니다.|
|[CPathT::RemoveFileSpec](#removefilespec)|에 해당 하는 경우 경로에서 후행 파일 이름과 백슬래시를 제거 하려면이 메서드를 호출 합니다.|
|[CPathT::RenameExtension](#renameextension)|새 확장을 사용 하 여 경로에 파일 이름 확장명을 바꾸려면이 메서드를 호출 합니다. 파일 이름 확장명이 없으면 확장 문자열의 끝에 연결 됩니다.|
|[CPathT::SkipRoot](#skiproot)|드라이브 문자나 UNC 서버/공유의 경로 부분을 무시 하는 경로 구문 분석 하려면이 메서드를 호출 합니다.|
|[CPathT::StripPath](#strippath)|정규화 된 경로 및 파일 이름의 경로 부분을 제거 하려면이 메서드를 호출 합니다.|
|[CPathT::StripToRoot](#striptoroot)|루트 정보를 제외 하 고 경로의 모든 부분을 제거 하려면이 메서드를 호출 합니다.|
|[CPathT::UnquoteSpaces](#unquotespaces)|경로의 시작과 끝에서 따옴표를 제거 하려면이 메서드를 호출 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CPathT::operator const StringType &](#operator_const_stringtype_amp)|이 연산자를 사용 하면 개체를 문자열로 처리 합니다.|
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|이 연산자를 사용 하면 개체를 문자열로 처리 합니다.|
|[CPathT::operator StringType &](#operator_stringtype_amp)|이 연산자를 사용 하면 개체를 문자열로 처리 합니다.|
|[CPathT::operator +=](#operator_add_eq)|이 연산자는 경로 문자열을 추가합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPathT::m_strPath](#m_strpath)|경로입니다.|

## <a name="remarks"></a>설명

`CPath`를 `CPathA`, 및 `CPathW` 의 인스턴스화는 `CPathT` 다음과 같이 정의 합니다.

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>요구 사항

**헤더:** atlpath.h의

##  <a name="addbackslash"></a>  CPathT::AddBackslash

경로 대 한 올바른 구문을 만들려면 문자열의 끝에 백슬래시를 추가 하려면이 메서드를 호출 합니다. 경로 후행 백슬래시 이미 있으면 백슬래시가 없습니다 추가 됩니다.

```
void AddBackslash();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathAddBackSlash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha)합니다.

##  <a name="addextension"></a>  CPathT::AddExtension

경로에 파일 확장명을 추가 하려면이 메서드를 호출 합니다.

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>매개 변수

*pszExtension*<br/>
추가할 파일 확장명입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona)합니다.

##  <a name="append"></a>  CPathT::Append

현재 경로에 문자열을 추가 하려면이 메서드를 호출 합니다.

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>매개 변수

*pszMore*<br/>
추가할 문자열입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda)합니다.

##  <a name="buildroot"></a>  CPathT::BuildRoot

지정 된 드라이브에서 루트 경로 만들려면이 메서드를 호출 합니다.

```
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>매개 변수

*iDrive*<br/>
드라이브 수 (0은 a:, 1은 b:, 및 등).

### <a name="remarks"></a>설명

자세한 내용은 [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota)합니다.

##  <a name="canonicalize"></a>  CPathT::Canonicalize

경로 정규 형식으로 변환 하려면이 메서드를 호출 합니다.

```
void Canonicalize();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea)합니다.

##  <a name="combine"></a>  CPathT::Combine

디렉터리 이름을 나타내는 문자열 및 하나의 경로에 파일 경로 이름을 나타내는 문자열을 연결 하려면이 메서드를 호출 합니다.

```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>매개 변수

*pszDir*<br/>
디렉터리 경로입니다.

*pszFile*<br/>
파일 경로입니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea)합니다.

##  <a name="commonprefix"></a>  CPathT::CommonPrefix

지정된 된 경로 현재 경로 사용 하 여 공통 접두사를 공유 하는지 여부를 확인 하려면이 메서드를 호출 합니다.

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>매개 변수

*pszOther*<br/>
현재 비교할 경로입니다.

### <a name="return-value"></a>반환 값

공통 접두사를 반환합니다.

### <a name="remarks"></a>설명

접두사를 이러한 형식 중 하나입니다. "C:\\\\", ".", "..", "..\\\\". 자세한 내용은 [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa)합니다.

##  <a name="compactpath"></a>  CPathT::CompactPath

줄임표를 사용 하 여 경로 구성 요소를 대체 하 여 지정 된 픽셀 너비 안에 맞도록 파일 경로 자를이 메서드를 호출 합니다.

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>매개 변수

*hDC*<br/>
글꼴 메트릭을 사용 하는 장치 컨텍스트.

*nWidth*<br/>
픽셀에서 너비에 맞게 해야만 하는 문자열입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha)합니다.

##  <a name="compactpathex"></a>  CPathT::CompactPathEx

줄임표를 사용 하 여 경로 구성 요소를 대체 하 여 지정된 된 문자 수 내에 맞게 파일 경로 자를이 메서드를 호출 합니다.

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>매개 변수

*nMaxChars*<br/>
NULL 종결 문자를 포함 하 여 새 문자열에 포함 될 문자의 최대 수입니다.

*dwFlags*<br/>
예약됨.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa)합니다.

##  <a name="cpatht"></a>  CPathT::CPathT

생성자입니다.

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>매개 변수

*pszPath*<br/>
경로 문자열에 대 한 포인터입니다.

*path*<br/>
경로 문자열입니다.

##  <a name="fileexists"></a>  CPathT::FileExists

이 경로 이름에 파일이 있는지 여부를 확인 하려면이 메서드를 호출 합니다.

```
BOOL FileExists() const;
```

### <a name="return-value"></a>반환 값

파일이 존재 하는지, FALSE 그렇지 않으면 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa)합니다.

##  <a name="findextension"></a>  CPathT::FindExtension

경로 내에서 파일 확장명의 위치를 찾으려면이 메서드를 호출 합니다.

```
int FindExtension() const;
```

### <a name="return-value"></a>반환 값

위치를 반환 합니다 "." 앞에 확장 합니다. 확장명이 있으면-1을 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona)합니다.

##  <a name="findfilename"></a>  CPathT::FindFileName

경로 내에서 파일 이름과 위치를 찾으려면이 메서드를 호출 합니다.

```
int FindFileName() const;
```

### <a name="return-value"></a>반환 값

파일 이름과 위치를 반환합니다. 파일 이름이 없으면-1을 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea)합니다.

##  <a name="getdrivenumber"></a>  CPathT::GetDriveNumber

'A'-'Z' 범위에서 드라이브 문자에 대 한 경로 검색 하 고 해당 드라이브 수를 반환 하려면이 메서드를 호출 합니다.

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>반환 값

있으면 경로 드라이브 문자 또는-1이 고, 그렇지 0에서 25 (에 해당 하 'A'-'Z') 까지의 정수로 드라이브 수를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera)합니다.

##  <a name="getextension"></a>  CPathT::GetExtension

경로에서 파일 확장명을 가져오려면이 메서드를 호출 합니다.

```
StringType GetExtension() const;
```

### <a name="return-value"></a>반환 값

파일 확장명을 반환합니다.

##  <a name="isdirectory"></a>  CPathT::IsDirectory

경로가 올바른 디렉터리 위치에 있는지 여부를 확인 하려면이 메서드를 호출 합니다.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>반환 값

경로 디렉터리의 경우 FALSE이 고, 그렇지 경우 0이 아닌 값 (16)를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya)합니다.

##  <a name="isfilespec"></a>  CPathT::IsFileSpec

모든 경로 구분 문자에 대 한 경로 검색 하려면이 메서드를 호출 (예를 들어, ':' 또는 '\\'). 경로 구분 문자가 있는 경우 경로 파일 사양 경로일으로 간주 됩니다.

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>반환 값

경로 내에서 경로 구분 문자가 없는 경우에 TRUE 또는 경로 구분 문자가 없으면 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca)합니다.

##  <a name="isprefix"></a>  CPathT::IsPrefix

전달 된 형식의 올바른 접두사를 경로 포함 되는지 여부를 확인 하려면이 메서드를 호출 *pszPrefix*합니다.

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>매개 변수

*pszPrefix*<br/>
검색할 접두사입니다. 접두사를 이러한 형식 중 하나입니다. "C:\\\\", ".", "..", "..\\\\".

### <a name="return-value"></a>반환 값

그렇지 않으면 경로 접두사 또는 FALSE 있으면 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa)합니다.

##  <a name="isrelative"></a>  CPathT::IsRelative

상대 경로 인지 확인 하려면이 메서드를 호출 합니다.

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>반환 값

경로 상대 또는 FALSE 절대 이면 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea)합니다.

##  <a name="isroot"></a>  CPathT::IsRoot

경로 디렉터리 루트 인지 확인 하려면이 메서드를 호출 합니다.

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>반환 값

경로 루트 또는 이면 FALSE이 고, 그렇지 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota)합니다.

##  <a name="issameroot"></a>  CPathT::IsSameRoot

다른 경로 현재 경로 사용 하 여 공통 루트 구성 요소에 있는지 여부를 확인 하려면이 메서드를 호출 합니다.

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>매개 변수

*pszOther*<br/>
다른 경로입니다.

### <a name="return-value"></a>반환 값

두 문자열을 동일한 루트 구성 요소 또는 있으면 FALSE이 고, 그렇지 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota)합니다.

##  <a name="isunc"></a>  CPathT::IsUNC

경로 서버에 대 한 유효한 UNC (범용 명명 규칙) 경로 인지 여부를 확인 하려면이 메서드를 호출 하 고 공유 합니다.

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>반환 값

경로가 올바른 UNC 경로 또는 FALSE 그렇지 않은 경우 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca)합니다.

##  <a name="isuncserver"></a>  CPathT::IsUNCServer

경로만 서버에 대 한 유효한 UNC (범용 명명 규칙) 경로 인지 여부를 확인 하려면이 메서드를 호출 합니다.

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>반환 값

않으면 문자열은 유효한 (공유 이름 없음)에 서버에 대 한 UNC 경로 또는 FALSE를 그렇지 않으면 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera)합니다.

##  <a name="isuncservershare"></a>  CPathT::IsUNCServerShare

올바른 UNC (범용 명명 규칙) 공유 경로 경로 인지 확인 하려면이 메서드를 호출 \\ \  *server*\ *공유*합니다.

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>반환 값

형태로 경로 이면 TRUE를 반환 합니다 \\ \  *server*\ *공유*, FALSE 또는 그렇지 않은 경우.

### <a name="remarks"></a>설명

자세한 내용은 [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea)합니다.

##  <a name="m_strpath"></a>  CPathT::m_strPath

경로입니다.

```
StringType m_strPath;
```

### <a name="remarks"></a>설명

`StringType` 템플릿 매개 변수를 `CPathT`입니다.

##  <a name="makepretty"></a>  CPathT::MakePretty

경로 경로 일관 된 모양을 제공 하는 모든 소문자를 변환 하려면이 메서드를 호출 합니다.

```
BOOL MakePretty();
```

### <a name="return-value"></a>반환 값

그렇지 않으면 경로 변환 된 경우 TRUE 또는 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya)합니다.

##  <a name="matchspec"></a>  CPathT::MatchSpec

와일드 카드 일치 유형을 포함 하는 문자열에 대 한 경로 검색 하려면이 메서드를 호출 합니다.

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>매개 변수

*pszSpec*<br/>
검색할 파일 형식 사용 하 여 null로 끝나는 문자열에 대 한 포인터입니다. 예를 들어 현재 경로에서 파일을 문서 파일 인지 여부를 테스트할 *pszSpec* 로 설정 해야 "*.doc"입니다.

### <a name="return-value"></a>반환 값

그렇지 않으면 문자열 일치 하는 경우 TRUE 또는 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca)합니다.

##  <a name="operator_add_eq"></a>  CPathT::operator +=

이 연산자는 경로 문자열을 추가합니다.

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>매개 변수

*pszMore*<br/>
추가할 문자열입니다.

### <a name="return-value"></a>반환 값

업데이트 된 경로 반환합니다.

##  <a name="operator_const_stringtype_amp"></a>  CPathT::operator const StringType &amp;

이 연산자를 사용 하면 개체를 문자열로 처리 합니다.

```
operator const StringType&() const throw();
```

### <a name="return-value"></a>반환 값

이 개체에 의해 관리 되는 현재 경로 나타내는 문자열을 반환 합니다.

##  <a name="operator_cpatht__pcxstr"></a>  CPathT::operator CPathT::PCXSTR

이 연산자를 사용 하면 개체를 문자열로 처리 합니다.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>반환 값

이 개체에 의해 관리 되는 현재 경로 나타내는 문자열을 반환 합니다.

##  <a name="operator_stringtype_amp"></a>  CPathT::operator StringType &amp;

이 연산자를 사용 하면 개체를 문자열로 처리 합니다.

```
operator StringType&() throw();
```

### <a name="return-value"></a>반환 값

이 개체에 의해 관리 되는 현재 경로 나타내는 문자열을 반환 합니다.

##  <a name="pcxstr"></a>  CPathT::PCXSTR

상수 문자열 형식입니다.

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>설명

`StringType` 템플릿 매개 변수를 `CPathT`입니다.

##  <a name="pxstr"></a>  CPathT::PXSTR

문자열 형식입니다.

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>설명

`StringType` 템플릿 매개 변수를 `CPathT`입니다.

##  <a name="quotespaces"></a>  CPathT::QuoteSpaces

이 메서드는 공백을 포함 하는 경우 경로를 따옴표로 묶습니다를 호출 합니다.

```
void QuoteSpaces();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa)합니다.

##  <a name="relativepathto"></a>  CPathT::RelativePathTo

다른 하나의 파일 또는 폴더에서 상대 경로 만들려면이 메서드를 호출 합니다.

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>매개 변수

*pszFrom*<br/>
시작 상대 경로입니다.

*dwAttrFrom*<br/>
파일 특성 *pszFrom*합니다. 이 값 FILE_ATTRIBUTE_DIRECTORY, 있으면 *pszFrom* 고, 그렇지 않으면 디렉터리 맡은 *pszFrom* 파일로 간주 됩니다.

*pszTo*<br/>
끝점의 상대 경로입니다.

*dwAttrTo*<br/>
파일 특성 *pszTo*합니다. 이 값 FILE_ATTRIBUTE_DIRECTORY, 있으면 *pszTo* 고, 그렇지 않으면 디렉터리 맡은 *pszTo* 파일로 간주 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa)합니다.

##  <a name="removeargs"></a>  CPathT::RemoveArgs

경로에서 명령줄 인수를 제거 하려면이 메서드를 호출 합니다.

```
void RemoveArgs();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa)합니다.

##  <a name="removebackslash"></a>  CPathT::RemoveBackslash

경로 후행 백슬래시를 제거 하려면이 메서드를 호출 합니다.

```
void RemoveBackslash();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha)합니다.

##  <a name="removeblanks"></a>  CPathT::RemoveBlanks

경로에서 모든 선행 및 후행 공백을 제거 하려면이 메서드를 호출 합니다.

```
void RemoveBlanks();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa)합니다.

##  <a name="removeextension"></a>  CPathT::RemoveExtension

있는 경우 경로에서 파일 확장명을 제거 하려면이 메서드를 호출 합니다.

```
void RemoveExtension();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona)합니다.

##  <a name="removefilespec"></a>  CPathT::RemoveFileSpec

에 해당 하는 경우 경로에서 후행 파일 이름과 백슬래시를 제거 하려면이 메서드를 호출 합니다.

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca)합니다.

##  <a name="renameextension"></a>  CPathT::RenameExtension

새 확장을 사용 하 여 경로에 파일 이름 확장명을 바꾸려면이 메서드를 호출 합니다. 파일 이름 확장명이 없으면 확장 경로 끝에 연결 됩니다.

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>매개 변수

*pszExtension*<br/>
새 파일 이름 확장명 앞에 "." 문자입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona)합니다.

##  <a name="skiproot"></a>  CPathT::SkipRoot

드라이브 문자나 UNC (범용 명명 규칙) 서버/공유의 경로 부분을 무시 하는 경로 구문 분석 하려면이 메서드를 호출 합니다.

```
int SkipRoot() const;
```

### <a name="return-value"></a>반환 값

루트 (드라이브 문자나 UNC 서버/공유) 뒤에 오는 하위 경로 부분에 대 한 위치를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota)합니다.

##  <a name="strippath"></a>  CPathT::StripPath

정규화 된 경로 및 파일 이름의 경로 부분을 제거 하려면이 메서드를 호출 합니다.

```
void StripPath();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha)합니다.

##  <a name="striptoroot"></a>  CPathT::StripToRoot

루트 정보를 제외 하 고 경로의 모든 부분을 제거 하려면이 메서드를 호출 합니다.

```
BOOL StripToRoot();
```

### <a name="return-value"></a>반환 값

TRUE 이면 올바른 드라이브 문자로 반환 경로에 또는 FALSE를 그렇지 않으면 발견 되었습니다.

### <a name="remarks"></a>설명

자세한 내용은 [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota)합니다.

##  <a name="unquotespaces"></a>  CPathT::UnquoteSpaces

경로의 시작과 끝에서 따옴표를 제거 하려면이 메서드를 호출 합니다.

```
void UnquoteSpaces();
```

### <a name="remarks"></a>설명

자세한 내용은 [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa)합니다.

##  <a name="xchar"></a>  CPathT::XCHAR

문자 형식입니다.

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>설명

`StringType` 템플릿 매개 변수를 `CPathT`입니다.

## <a name="see-also"></a>참고자료

[클래스](../../atl/reference/atl-classes.md)<br/>
[CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)
