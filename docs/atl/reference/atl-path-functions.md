---
title: ATL 경로 함수
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, path
f1_keywords:
- ATLPATH/ATL::ATLPath::AddBackslash
- ATLPATH/ATL::ATLPath::AddExtension
- ATLPATH/ATL::ATLPath::Append
- ATLPATH/ATL::ATLPath::BuildRoot
- ATLPATH/ATL::ATLPath::Canonicalize
- ATLPATH/ATL::ATLPath::Combine
- ATLPATH/ATL::ATLPath::CommonPrefix
- ATLPATH/ATL::ATLPath::CompactPath
- ATLPATH/ATL::ATLPath::CompactPathEx
- ATLPATH/ATL::ATLPath::FileExists
- ATLPATH/ATL::ATLPath::FindExtension
- ATLPATH/ATL::ATLPath::FindFileName
- ATLPATH/ATL::ATLPath::GetDriveNumber
- ATLPATH/ATL::ATLPath::IsDirectory
- ATLPATH/ATL::ATLPath::IsFileSpec
- ATLPATH/ATL::ATLPath::IsPrefix
- ATLPATH/ATL::ATLPath::IsRelative
- ATLPATH/ATL::ATLPath::IsRoot
- ATLPATH/ATL::ATLPath::IsSameRoot
- ATLPATH/ATL::ATLPath::IsUNC
- ATLPATH/ATL::ATLPath::IsUNCServer
- ATLPATH/ATL::ATLPath::IsUNCServerShare
- ATLPATH/ATL::ATLPath::MakePretty
- ATLPATH/ATL::ATLPath::MatchSpec
- ATLPATH/ATL::ATLPath::QuoteSpaces
- ATLPATH/ATL::ATLPath::RelativePathTo
- ATLPATH/ATL::ATLPath::RemoveArgs
- ATLPATH/ATL::ATLPath::RemoveBackslash
- ATLPATH/ATL::ATLPath::RemoveBlanks
- ATLPATH/ATL::ATLPath::RemoveExtension
- ATLPATH/ATL::ATLPath::RemoveFileSpec
- ATLPATH/ATL::ATLPath::RenameExtension
- ATLPATH/ATL::ATLPath::SkipRoot
- ATLPATH/ATL::ATLPath::StripPath
- ATLPATH/ATL::ATLPath::StripToRoot
- ATLPATH/ATL::ATLPath::UnquoteSpaces
ms.assetid: d1ec2b8d-7ec7-43ea-90dd-0a740d2a742b
ms.openlocfilehash: 683fd9c6464187e416ea032840507b2062de1fa3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248192"
---
# <a name="atl-path-functions"></a>ATL 경로 함수

형식의 경로 조작 하기 위한 ATLPath 클래스를 제공 하는 ATL [CPathT](cpatht-class.md)합니다. Atlpath.h의에이 코드를 찾을 수 있습니다.

### <a name="related-classes"></a>관련된 클래스

|||
|-|-|
|[CPathT 클래스](cpatht-class.md)|이 클래스는 경로 나타냅니다.|

### <a name="related-typedefs"></a>관련된 형식 정의

|||
|-|-|
|`CPath`|특수화 [CPathT](cpatht-class.md) 사용 하 여 `CString`입니다.|
|`CPathA`|특수화 [CPathT](cpatht-class.md) 사용 하 여 `CStringA`입니다.|
|`CPathW`|특수화 [CPathT](cpatht-class.md) 사용 하 여 `CStringW`입니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[ATLPath::AddBackslash](#addbackslash)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha)합니다.|
|[ATLPath::AddExtension](#addextension)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona)합니다.|
|[ATLPath::Append](#append)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda)합니다.|
|[ATLPath::BuildRoot](#buildroot)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota)합니다.|
|[ATLPath::Canonicalize](#canonicalize)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea)합니다.|
|[ATLPath::Combine](#combine)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea)합니다.|
|[ATLPath::CommonPrefix](#commonprefix)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa)합니다.|
|[ATLPath::CompactPath](#compactpath)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha)합니다.|
|[ATLPath::CompactPathEx](#compactpathex)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa)합니다.|
|[ATLPath::FileExists](#fileexists)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa)합니다.|
|[ATLPath::FindExtension](#findextension)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona)합니다.|
|[ATLPath::FindFileName](#findfilename)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea)합니다.|
|[ATLPath::GetDriveNumber](#getdrivenumber)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera)합니다.|
|[ATLPath::IsDirectory](#isdirectory)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya)합니다.|
|[ATLPath::IsFileSpec](#isfilespec)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca)합니다.|
|[ATLPath::IsPrefix](#isprefix)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa)합니다.|
|[ATLPath::IsRelative](#isrelative)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea)합니다.|
|[ATLPath::IsRoot](#isroot)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota)합니다.|
|[ATLPath::IsSameRoot](#issameroot)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota)합니다.|
|[ATLPath::IsUNC](#isunc)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca)합니다.|
|[ATLPath::IsUNCServer](#isuncserver)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera)합니다.|
|[ATLPath::IsUNCServerShare](#isuncservershare)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea)합니다.|
|[ATLPath::MakePretty](#makepretty)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya)합니다.|
|[ATLPath::MatchSpec](#matchspec)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca)합니다.|
|[ATLPath::QuoteSpaces](#quotespaces)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa)합니다.|
|[ATLPath::RelativePathTo](#relativepathto)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa)합니다.|
|[ATLPath::RemoveArgs](#removeargs)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa)합니다.|
|[ATLPath::RemoveBackslash](#removebackslash)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha)합니다.|
|[ATLPath::RemoveBlanks](#removeblanks)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa)합니다.|
|[ATLPath::RemoveExtension](#removeextension)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona)합니다.|
|[ATLPath::RemoveFileSpec](#removefilespec)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca)합니다.|
|[ATLPath::RenameExtension](#renameextension)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona)합니다.|
|[ATLPath::SkipRoot](#skiproot)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota)합니다.|
|[ATLPath::StripPath](#strippath)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha)합니다.|
|[ATLPath::StripToRoot](#striptoroot)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota)합니다.|
|[ATLPath::UnquoteSpaces](#unquotespaces)|이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa)합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlpath.h의

## <a name="addbackslash"></a> ATLPath::AddBackSlash

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha)합니다.

### <a name="syntax"></a>구문

```
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha) 세부 정보에 대 한 합니다.

## <a name="addextension"></a> ATLPath::AddExtension

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona)합니다.

### <a name="syntax"></a>구문

```
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>설명

참조 [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona) 세부 정보에 대 한 합니다.

## <a name="append"></a> ATLPath::Append

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda)합니다.

### <a name="syntax"></a>구문

```
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>설명

참조 [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda) 세부 정보에 대 한 합니다.

## <a name="buildroot"></a> ATLPath::BuildRoot

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota)합니다.

### <a name="syntax"></a>구문

```
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>설명

참조 [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota) 세부 정보에 대 한 합니다.

## <a name="canonicalize"></a> ATLPath::Canonicalize

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea)합니다.

### <a name="syntax"></a>구문

```
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>설명

참조 [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea) 세부 정보에 대 한 합니다.

## <a name="combine"></a> ATLPath::Combine

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea)합니다.

### <a name="syntax"></a>구문

```
inline char* Combine(
   char* pszDest,
   const char* pszDir,
   const char* pszFile
);

inline wchar_t* Combine(
   wchar_t* pszDest,
   const wchar_t* pszDir,
   const wchar_t* pszFile);
```

### <a name="remarks"></a>설명

자세한 PathCombine를 참조 하세요.

## <a name="commonprefix"></a> ATLPath::CommonPrefix

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa)합니다.

### <a name="syntax"></a>구문

```
inline int CommonPrefix(
   const char* pszFile1,
   const char* pszFile2,
   char* pszDest);

inline int CommonPrefix(
   const wchar_t* pszFile1,
   const wchar_t* pszFile2,
   wchar_t* pszDest);
```

### <a name="remarks"></a>설명

참조 [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa) 세부 정보에 대 한 합니다.

## <a name="compactpath"></a> ATLPath::CompactPath

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha)합니다.

### <a name="syntax"></a>구문

```
inline BOOL CompactPath(
   HDC hDC,
   char* pszPath,
   UINT dx);

inline BOOL CompactPath(
   HDC hDC,
   wchar_t* pszPath,
   UINT dx);
```

### <a name="remarks"></a>설명

참조 [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha) 세부 정보에 대 한 합니다.

## <a name="compactpathex"></a> ATLPath::CompactPathEx

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa)합니다.

### <a name="syntax"></a>구문

```
inline BOOL CompactPathEx(
   char* pszDest,
   const char* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);

inline BOOL CompactPathEx(
   wchar_t* pszDest,
   const wchar_t* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);
```

### <a name="remarks"></a>설명

참조 [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa) 세부 정보에 대 한 합니다.

## <a name="fileexists"></a> ATLPath::FileExists

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa)합니다.

### <a name="syntax"></a>구문

```
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa) 세부 정보에 대 한 합니다.

## <a name="findextension"></a> ATLPath::FindExtension

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona)합니다.

### <a name="syntax"></a>구문

```
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona) 세부 정보에 대 한 합니다.

## <a name="findfilename"></a> ATLPath::FindFileName

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea)합니다.

### <a name="syntax"></a>구문

```
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) 세부 정보에 대 한 합니다.

## <a name="getdrivenumber"></a> ATLPath::GetDriveNumber

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera)합니다.

### <a name="syntax"></a>구문

```
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera) 세부 정보에 대 한 합니다.

## <a name="isdirectory"></a>  ATLPath::IsDirectory

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya)합니다.

```
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

자세한 PathIsDirectory를 참조 하세요.

## <a name="isfilespec"></a> ATLPath::IsFileSpec

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca)합니다.

### <a name="syntax"></a>구문

```
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca) 세부 정보에 대 한 합니다.

## <a name="isprefix"></a> ATLPath::IsPrefix

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa)합니다.

### <a name="syntax"></a>구문

```
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa) 세부 정보에 대 한 합니다.

## <a name="isrelative"></a> ATLPath::IsRelative

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea)합니다.

### <a name="syntax"></a>구문

```
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea) 세부 정보에 대 한 합니다.

## <a name="isroot"></a> ATLPath::IsRoot

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota)합니다.

### <a name="syntax"></a>구문

```
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota) 세부 정보에 대 한 합니다.

## <a name="issameroot"></a> ATLPath::IsSameRoot

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota)합니다.

### <a name="syntax"></a>구문

```
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>설명

참조 [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota) 세부 정보에 대 한 합니다.

## <a name="isunc"></a> ATLPath::IsUNC

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca)합니다.

### <a name="syntax"></a>구문

```
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca) 세부 정보에 대 한 합니다.

## <a name="isuncserver"></a> ATLPath::IsUNCServer

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera)합니다.

### <a name="syntax"></a>구문

```
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera) 세부 정보에 대 한 합니다.

## <a name="isuncservershare"></a> ATLPath::IsUNCServerShare

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea)합니다.

### <a name="syntax"></a>구문

```
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea) 세부 정보에 대 한 합니다.

## <a name="makepretty"></a> ATLPath::MakePretty

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya)합니다.

### <a name="syntax"></a>구문

```
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya) 세부 정보에 대 한 합니다.

## <a name="matchspec"></a> ATLPath::MatchSpec

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca)합니다.

### <a name="syntax"></a>구문

```
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>설명

참조 [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca) 세부 정보에 대 한 합니다.

## <a name="quotespaces"></a> ATLPath::QuoteSpaces

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa)합니다.

### <a name="syntax"></a>구문

```
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa) 세부 정보에 대 한 합니다.

## <a name="relativepathto"></a> ATLPath::RelativePathTo

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa)합니다.

### <a name="syntax"></a>구문

```
inline BOOL RelativePathTo(
   char* pszPath,
   const char* pszFrom,
   DWORD dwAttrFrom,
   const char* pszTo,
   DWORD dwAttrTo);

inline BOOL RelativePathTo(
   wchar_t* pszPath,
   const wchar_t* pszFrom,
   DWORD dwAttrFrom,
   const wchar_t* pszTo,
   DWORD dwAttrTo);
```

### <a name="remarks"></a>설명

참조 [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa) 세부 정보에 대 한 합니다.

## <a name="removeargs"></a> ATLPath::RemoveArgs

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa)합니다.

### <a name="syntax"></a>구문

```
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa) 세부 정보에 대 한 합니다.

## <a name="removebackslash"></a> ATLPath::RemoveBackslash

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha)합니다.

### <a name="syntax"></a>구문

```
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha) 세부 정보에 대 한 합니다.

## <a name="removeblanks"></a> ATLPath::RemoveBlanks

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa)합니다.

### <a name="syntax"></a>구문

```
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa) 세부 정보에 대 한 합니다.

## <a name="removeextension"></a> ATLPath::RemoveExtension

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona)합니다.

### <a name="syntax"></a>구문

```
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona) 세부 정보에 대 한 합니다.

## <a name="removefilespec"></a> ATLPath::RemoveFileSpec

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca)합니다.

### <a name="syntax"></a>구문

```
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca) 세부 정보에 대 한 합니다.

## <a name="renameextension"></a> ATLPath::RenameExtension

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona)합니다.

### <a name="syntax"></a>구문

```
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>설명

참조 [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona) 세부 정보에 대 한 합니다.

## <a name="skiproot"></a> ATLPath::SkipRoot

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota)합니다.

### <a name="syntax"></a>구문

```
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota) 세부 정보에 대 한 합니다.

## <a name="strippath"></a> ATLPath::StripPath

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha)합니다.

### <a name="syntax"></a>구문

```
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha) 세부 정보에 대 한 합니다.

## <a name="striptoroot"></a> ATLPath::StripToRoot

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota)합니다.

### <a name="syntax"></a>구문

```
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota) 세부 정보에 대 한 합니다.

## <a name="unquotespaces"></a> ATLPath::UnquoteSpaces

이 함수는에 대 한는 오버 로드 된 래퍼입니다 [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa)합니다.

### <a name="syntax"></a>구문

```
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>설명

참조 [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa) 세부 정보에 대 한 합니다.
