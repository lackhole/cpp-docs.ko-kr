---
title: 가져오기 바인딩
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
ms.openlocfilehash: 4058d738b87b69a73e8f18d977be8435a7d96a14
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57819851"
---
# <a name="binding-imports"></a>가져오기 바인딩

링커의 기본 동작은 지연 로드 된 dll을 바인딩할 수 있는 가져오기 주소 테이블을 만드는 방법은입니다. 도우미 함수를 호출 하는 대신 바인딩된 정보를 사용 하려고 경우 DLL이 바인딩되면 **GetProcAddress** 참조 된 각 합니다. 타임 스탬프 또는 기본 설정된 주소가 일치 하지 않으면 로드 된 DLL의 도우미 함수 것으로 간주 하 바인딩된 가져오기 주소 테이블을 오래 된 존재 하지 않는 경우에 따라 진행 됩니다.

지정 하지 않을 경우 DLL의 지연 로드 가져오기 바인딩할 합니다 [지연/](delay-delay-load-import-settings.md): nobind 링커의 명령줄에서 이미지 파일의 생성 및 사용 중인 공간에서 바인딩된 가져오기 주소 테이블을 못합니다.

## <a name="see-also"></a>참고자료

[링커의 지연 로드된 DLL 지원](linker-support-for-delay-loaded-dlls.md)
