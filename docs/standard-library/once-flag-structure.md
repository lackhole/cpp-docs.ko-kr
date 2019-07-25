---
title: once_flag 구조체
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: fb85bd48f9b1ac10ec2fefbc6738aae777f67bcf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455201"
---
# <a name="onceflag-structure"></a>once_flag 구조체

실행 스레드가 여러 개 있는 경우에도 초기화 코드를 한 번만 호출 하도록 템플릿 함수 [call_once](../standard-library/mutex-functions.md#call_once) 에 사용 되는 **구조체** 를 나타냅니다.

## <a name="syntax"></a>구문

struct once_flag { constexpr once_flag() noexcept; };

## <a name="remarks"></a>설명

`once_flag` **구조체** 에는 기본 생성자만 있습니다.

`once_flag` 형식의 개체는 만들 수는 있지만 복사할 수는 없습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<뮤텍스 >

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
