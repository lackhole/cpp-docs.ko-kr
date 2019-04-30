---
title: '방법: COM 구성 요소를 사용 하는 격리 된 응용 프로그램 빌드'
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
ms.openlocfilehash: 01b5c7056bd10a7c1f88df74b5c6b4aa78ff3fde
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273562"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>방법: COM 구성 요소를 사용 하는 격리 된 응용 프로그램 빌드

격리 된 응용 프로그램은 프로그램에서 기본 제공 하는 매니페스트를가 하는 응용 프로그램. COM 구성 요소를 사용 하는 격리 된 응용 프로그램을 만들 수 있습니다.

### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>격리 된 응용 프로그램의 매니페스트를 COM 참조를 추가 하려면

1. 격리 된 응용 프로그램에 대 한 프로젝트 속성 페이지를 엽니다.

1. **구성 속성 노드**를 확장한 다음 **매니페스트 도구** 노드를 확장합니다.

1. 선택 합니다 **격리 COM** 속성 페이지 및 설정 합니다 **구성 요소 파일 이름** 속성을 격리 된 응용 프로그램에서 사용 하는 COM 구성 요소의 이름입니다.

1. **확인**을 클릭합니다.

### <a name="to-build-manifests-into-isolated-applications"></a>격리 된 응용 프로그램에 매니페스트를 빌드

1. 격리 된 응용 프로그램에 대 한 프로젝트 속성 페이지를 엽니다.

1. **구성 속성 노드**를 확장한 다음 **매니페스트 도구** 노드를 확장합니다.

1. **입력 및 출력** 속성 페이지를 선택한 다음 **매니페스트 포함** 속성을 **예**로 설정합니다.

1. **확인**을 클릭합니다.

1. 솔루션을 빌드합니다.

## <a name="see-also"></a>참고자료

[격리된 응용 프로그램](/windows/desktop/SbsCs/isolated-applications)<br/>
[Side-by-side 어셈블리](/windows/desktop/SbsCs/about-side-by-side-assemblies-)
