---
title: 명령줄 오류 D8037
ms.date: 11/04/2016
f1_keywords:
- D8037
helpviewer_keywords:
- D8037
ms.assetid: acddaaa0-bd84-426f-a37b-8f680b379c9d
ms.openlocfilehash: f9f099d1abb8529620c1b3a0bc14705463ca5cd0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59021484"
---
# <a name="command-line-error-d8037"></a>명령줄 오류 D8037

임시 il 파일을 만들 수 없습니다. 정리 임시 디렉터리에 있는 기존 il 파일

임시 컴파일러 중간 파일을 만드는 데 충분 한 공간이 아닙니다. 이 오류를 해결 하려면 지정 된 디렉터리에 이전 MSIL 파일을 제거 합니다 **TMP** 환경 변수입니다. 이러한 파일 형식 _CL_hhhhhhhh.ss, 여기서 h는 임의의 16 진수 이며 ss IL 파일의 형식을 나타내는 됩니다. 또한 최신 운영 체제 패치를 사용 하 여 컴퓨터를 업데이트 해야 합니다.

## <a name="see-also"></a>참고자료

[명령줄 오류(D8000 ~ D9999)](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC 컴파일러 옵션](../../build/reference/compiler-options.md)