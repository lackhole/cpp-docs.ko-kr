---
title: '방법: COM 구성 요소를 사용 하는 격리 된 응용 프로그램 빌드'
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
ms.openlocfilehash: 8ae3c51502267f202cbb85ea7be2a81dc3310410
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493244"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>방법: COM 구성 요소를 사용 하는 격리 된 응용 프로그램 빌드

격리 된 응용 프로그램은 매니페스트가 프로그램에 기본 제공 되는 응용 프로그램입니다. COM 구성 요소를 사용 하는 격리 된 응용 프로그램을 만들 수 있습니다.

### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>격리 된 응용 프로그램의 매니페스트에 COM 참조를 추가 하려면

1. 격리 된 응용 프로그램에 대 한 프로젝트 속성 페이지를 엽니다.

1. **구성 속성 노드**를 확장한 다음 **매니페스트 도구** 노드를 확장합니다.

1. 격리 된 **com** 속성 페이지를 선택한 다음 **구성 요소 파일 이름** 속성을 격리 된 응용 프로그램에서 사용할 COM 구성 요소의 이름으로 설정 합니다.

1. **확인**을 클릭합니다.

### <a name="to-build-manifests-into-isolated-applications"></a>격리 된 응용 프로그램에 매니페스트를 빌드하려면

1. 격리 된 응용 프로그램에 대 한 프로젝트 속성 페이지를 엽니다.

1. **구성 속성 노드**를 확장한 다음 **매니페스트 도구** 노드를 확장합니다.

1. **입력 및 출력** 속성 페이지를 선택한 다음 **매니페스트 포함** 속성을 **예**로 설정합니다.

1. **확인**을 클릭합니다.

1. 솔루션을 빌드합니다.

## <a name="see-also"></a>참고자료

[격리된 응용 프로그램](/windows/win32/SbsCs/isolated-applications)<br/>
[Side-by-side 어셈블리](/windows/win32/SbsCs/about-side-by-side-assemblies-)
