---
title: include () 특성 가져오기
ms.date: 08/29/2019
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: 39ab63525b2b83781cbcaf86a61742c5fb767b72
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218876"
---
# <a name="include-import-attribute"></a>include () 특성 가져오기

**C++컴퓨터별**

자동 제외를 사용하지 않도록 설정합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **include ("** _Name1_ **"** [ __, "__ *Name2* __"__ ...] __)__

### <a name="parameters"></a>매개 변수

*Name1*\
강제로 포함할 첫 번째 항목입니다.

*Name2*\
필요할 경우 강제로 포함할 두 번째 항목입니다.

## <a name="remarks"></a>설명

형식 라이브러리가 시스템 헤더 또는 다른 형식 라이브러리에 정의된 항목 정의를 포함할 수 있습니다. `#import`는 다양한 정의 오류를 자동으로 제외하여 해당 오류를 방지하려고 합니다. 일부 항목을 자동으로 제외 하지 않아야 하는 경우 [컴파일러 경고 (수준 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)가 표시 될 수 있습니다. 이 특성을 사용 하 여 자동 제외를 사용 하지 않도록 설정할 수 있습니다. 이 특성은 포함할 형식 라이브러리 항목의 각 이름에 대해 하나씩, 여러 개의 인수를 사용할 수 있습니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
