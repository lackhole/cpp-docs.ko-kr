---
title: /ZH (디버그 정보의 파일 체크섬 계산에 대 한 해시 알고리즘)
description: /ZH 컴파일러 옵션을 사용 하 여 디버그 정보에서 MD5, SHA-1 또는 SHA-256 소스 파일 체크섬을 사용 하도록 설정 합니다.
ms.date: 09/16/2019
f1_keywords:
- /ZH
- /ZH:MD5
- /ZH:SHA1
- /ZH:SHA_256
helpviewer_keywords:
- /ZH
- /ZH:MD5
- /ZH:SHA1
- /ZH:SHA_256
- /ZH compiler option
- /ZH:MD5 compiler option
- /ZH:SHA1 compiler option
- /ZH:SHA_256 compiler option
- Hash algorithm for file checksum in debug info
ms.openlocfilehash: f05dc2bc3b8ce4502ff16a6e19fdbb10763b34ba
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686937"
---
# <a name="zh-hash-algorithm-for-calculation-of-file-checksum-in-debug-info"></a>/ZH (디버그 정보의 파일 체크섬 계산에 대 한 해시 알고리즘)

각 소스 파일에 대 한 체크섬을 생성 하는 데 사용할 암호화 해시 알고리즘을 지정 합니다.

## <a name="syntax"></a>구문

> **/ZH:** {**MD5**|**SHA1**|**SHA_256**}

## <a name="arguments"></a>인수

**/ZH: MD5**\
체크섬에 MD5 해시를 사용 합니다. 이 옵션은 기본값입니다.

**/ZH: SHA1**\
체크섬에 SHA-1 해시를 사용 합니다.

**/ZH: SHA_256**\
체크섬에 대해 SHA-256 해시를 사용 합니다.

## <a name="remarks"></a>설명

PDB 파일에는 연결 된 실행 파일의 개체 코드로 컴파일된 각 소스 파일에 대 한 체크섬이 저장 됩니다. 체크섬을 사용 하면 디버거가 로드 하는 소스 코드가 실행 파일과 일치 하는지 확인할 수 있습니다. 컴파일러 및 디버거는 MD5, SHA-1 및 SHA-256 해시 알고리즘을 지원 합니다. 기본적으로 컴파일러는 MD5 해시를 사용 하 여 체크섬을 생성 합니다. 이 옵션은 **/Zh: MD5** 옵션을 사용 하 여 명시적으로 지정할 수 있습니다.

MD5 및 s h a-1에서 충돌 문제가 발생할 수 있으므로, **/zh: SHA_256** 옵션을 사용 하는 것이 좋습니다. SHA-256 해시는 컴파일 시간이 약간 늘어날 수 있습니다.

둘 이상의 **/Zh** 옵션을 지정 하면 마지막 옵션이 사용 됩니다.

**/Zh** 옵션은 Visual Studio 2019 버전 16.4부터 사용할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성** 드롭다운을 **모든 구성**으로 설정 합니다.

1. **구성 속성** > **C/C++**  > **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션** 속성을 수정 하 여 **/ZH: MD5**, **/Zh: SHA1**또는 **/zh: SHA_256** 옵션을 추가 하 고 **확인**을 선택 합니다.

## <a name="see-also"></a>참조

[컴파일러 옵션](compiler-options.md)\
[원본 서버](/windows/win32/debug/source-server-and-source-indexing)
