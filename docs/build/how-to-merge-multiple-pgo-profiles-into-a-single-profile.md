---
title: '방법: 여러 개의 PGO 프로필을 단일 프로필로 병합'
ms.date: 03/14/2018
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
ms.openlocfilehash: 451c0f30a271f5dce3974e172766da4a23340b93
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826942"
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>방법: 여러 개의 PGO 프로필을 단일 프로필로 병합

프로필 기반 최적화 PGO ()는 프로 파일링 된 시나리오를 기반으로 하는 최적화 된 이진 파일을 만들기 위한 훌륭한 도구입니다. 하지만 몇 가지 중요 한, 아직 고유 시나리오는 응용 프로그램 해야 될까요? 다양 한 시나리오에서 PGO 사용할 수 있는 단일 프로필을 만들려면 어떻게 해야 있습니다? Visual studio에서 PGO Manager [pgomgr.exe](pgomgr.md),이 작업을 수행 합니다.

프로필 병합에 대 한 구문은 다음과 같습니다.

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

여기서 `num` 은이 병합 하 여 추가 된.pgc 파일에 대 한 사용 하는 선택적 가중치입니다. 가중치는 다른 항목 보다 더 중요 한 몇 가지 시나리오 또는 시나리오 여러 번 실행 하는 경우에 주로 사용 됩니다.

> [!NOTE]
> PGO 관리자는 오래 된 프로필 데이터와 함께 작동 하지 않습니다. .Pgc 파일.pgd 파일로 병합할.pgc 파일.pgd 파일을 생성 하는 동일한 링크 호출에 의해 생성 된 실행 개체에 의해 생성 되어야 합니다.

## <a name="examples"></a>예제

PGO 관리자는이 예제에서는 6 번 pgdFile.pgd에 pgcFile.pgc 추가 됩니다.

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

이 예제에서는 PGO 관리자를 pgcFile1.pgc 및 pgcFile2.pgc 각.pgc 파일에 대해 두 번 pgdFile.pgd를에 추가 합니다.

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

.Pgc 파일 인수 없이 실행 되는 PGO 관리자 뒤에 느낌표 (!)와 하나 이상의 다음 임의의 문자.pgd 파일로 동일한 기본 이름을 가진 모든.pgc 파일에 대 한 로컬 디렉터리를 검색 합니다. 예를 들어, 파일 test.pgd, test!1.pgc, test2.pgc, 및 test!hello.pgc를 로컬 디렉터리에 있으며 다음 명령은 로컬 디렉터리에서 다음 실행 **pgomgr** test.pgd test!1.pgc 및 test!hello.pgc 병합 합니다.

`pgomgr /merge test.pgd`

## <a name="see-also"></a>참고자료

[프로필 기반 최적화](profile-guided-optimizations.md)
