---
title: Concurrency 네임 스페이스 상수 (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::HLSL_MAX_NUM_BUFFERS
- amp/Concurrency::MODULENAME_MAX_LENGTH
ms.assetid: 13a8e8cd-2eec-4e60-a91d-5d271072747b
ms.openlocfilehash: c6cdaa36f481bd4a703981bfa1bc0617860b0917
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348551"
---
# <a name="concurrency-namespace-constants-amp"></a>Concurrency 네임 스페이스 상수 (AMP)

|||
|-|-|
|[HLSL_MAX_NUM_BUFFERS](#hlsl_max_num_buffers)|[MODULENAME_MAX_LENGTH](#modulename_max_length)|

##  <a name="hlsl_max_num_buffers"></a>  HLSL_MAX_NUM_BUFFERS Constant

Directx 로부터 허용 되는 버퍼의 최대 수입니다.

```
static const UINT HLSL_MAX_NUM_BUFFERS = 64 + 128;
```

##  <a name="modulename_max_length"></a>  MODULENAME_MAX_LENGTH 상수

모듈 이름의 최대 길이 저장합니다. 이 값은 컴파일러와 런타임에서 동일해야 합니다.

```
static const UINT MODULENAME_MAX_LENGTH = 1024;
```

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
