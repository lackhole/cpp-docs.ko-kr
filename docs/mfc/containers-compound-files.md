---
title: '컨테이너: 복합 파일'
ms.date: 11/04/2016
helpviewer_keywords:
- compound files [MFC]
- compound documents
- containers [MFC], compound files
- OLE documents [MFC], compound files
- performance [MFC], compound files
- files [MFC], compound
- standardized file structure compound files
- documents [MFC], compound
- documents [MFC], OLE
- OLE containers [MFC], compound files
- access modes for files [MFC]
ms.assetid: 8b83cb3e-76c8-4bbe-ba16-737092b36f49
ms.openlocfilehash: 8ae701af3dbf45a1b48ef223f421d17f6abee213
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152620"
---
# <a name="containers-compound-files"></a>컨테이너: 복합 파일

이 문서에서는 구성 요소 및 복합 파일의 구현과 OLE 응용 프로그램에서 복합 파일을 사용할 때의 단점을 설명 합니다.

복합 파일은 OLE의 필수적인 부분입니다. 데이터 전송 및 OLE 문서 저장소를 용이 하 게 사용 됩니다. 복합 파일은 활성 구조화 된 저장소 모델의 구현입니다. 일관 된 인터페이스에는 저장소, 스트림 또는 파일 개체를 직렬화를 해당 지원 존재합니다. 복합 파일에서에서 지원 되는 Microsoft Foundation Class 라이브러리 클래스 `COleStreamFile` 고 `COleDocument`입니다.

> [!NOTE]
>  복합 파일을 사용 한다고 해 서 OLE 문서 또는 복합 문서에서 정보를 가져오는 것은 아닙니다. 복합 파일은 복합 문서, OLE 문서 및 기타 데이터를 저장 하는 방법 중 하나일 뿐입니다.

##  <a name="_core_components_of_a_compound_file"></a> 복합 파일의 구성 요소

OLE 복합 파일 구현의 세 가지 개체 유형이 사용: 스트림 개체, 저장소 개체 및 `ILockBytes` 개체입니다. 이러한 개체는 다음과 같은 방법으로 표준 파일 시스템의 구성 요소와 비슷합니다.

- 파일과 마찬가지로 Stream 개체, 모든 형식의 데이터를 저장합니다.

- 디렉터리 등의 저장소 개체를 다른 저장소 및 스트림 개체를 포함할 수 있습니다.

- `LockBytes` 개체는 저장소 개체와 실제 하드웨어 간의 인터페이스를 나타냅니다. 실제 바이트 수를 원하는 저장소 장치에 작성 되는 방법 결정을 `LockBytes` 하드 드라이브 또는 전역 메모리 영역을 같은 개체에 액세스 합니다. 에 대 한 자세한 내용은 `LockBytes` 개체 및 `ILockBytes` 인터페이스를 참조 합니다 *OLE 프로그래머 참조*합니다.

##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> 복합 파일의 장점 및 단점

복합 파일 file storage의 이전 메서드를 사용 하 여 혜택을 사용할 수 없습니다를 제공합니다. 다음과 같은 변경 내용이 해당됩니다.

- 파일에 액세스 합니다.

- 파일 액세스 모드입니다.

- 파일 구조를 표준화 합니다.

복합 파일의 잠재적인 단점-플로피 디스크의 저장소와 관련 된 큰 크기 및 성능 문제-해야 수로 간주 여부를 결정 하려면 응용 프로그램에서 사용 하 합니다.

###  <a name="_core_incremental_access_to_files"></a> 파일에 대 한 증분 액세스

파일에 대 한 증분 액세스 장점은 자동 복합 파일을 사용 합니다. "파일 내에서 파일 시스템"으로 복합 파일을 볼 수 있습니다, 스트림 또는 storage와 같은 개별 개체 유형이 전체 파일을 로드 하지 않아도 액세스할 수 있습니다. 사용자가 편집을 위해 새 개체에 액세스 해야 하는 응용 프로그램 시간을 크게 줄일 수이 합니다. 증분 업데이트를 기반으로 동일한 개념을 유사한 이점 제공 합니다. 하나의 개체에 대 한 변경 내용을 저장 하기 위해 전체 파일을 저장 하는 대신 OLE 스트림 또는 저장소 개체에만 사용자가 편집을 저장 합니다.

###  <a name="_core_file_access_modes"></a> 파일 액세스 모드

복합 파일을 사용 하는 또 다른 이점은 복합 파일에 개체 변경 내용을 디스크에 커밋하는 시점을 확인할 수 있게 합니다. 파일 액세스 되는, 트랜잭션 또는 직접 모드를 변경 내용이 커밋될 때를 결정 합니다.

- 트 랜 잭 트 모드 저장 하거나 변경을 취소 하 고 사용자가 선택 될 때까지 기존 및 새 사용할 수 있는 문서 복사본을 유지 하므로 복합 파일에서 개체를 변경 하려면 2 단계 커밋 작업을 사용 합니다.

- 직접 모드는 나중에 해당 변경 내용을 취소 하는 기능이 없으면 현재 변경이 문서의 변경 내용을 통합 합니다.

액세스 모드에 대 한 자세한 내용은 참조는 *참조 OLE Programmer's Reference*합니다.

###  <a name="_core_standardization"></a> 표준화

복합 파일의 표준화 된 구조에 다른 OLE 응용 프로그램을 실제로 파일을 만든 응용 프로그램의 알지 OLE 응용 프로그램에서 만든 복합 파일을 통해 이동할 수 있습니다.

###  <a name="_core_size_and_performance_considerations"></a> 크기 및 성능 고려 사항

복합 파일 저장소 구조 및 데이터를 증분 방식으로 저장 하는 기능 복잡성으로 인해이 형식을 사용 하 여 파일이 다른 파일 보다 클 수 경향이 구조화 되지 않은 데이터를 사용 하 여 또는 저장소 "플랫 파일"입니다. 응용 프로그램는 자주 로드 하 고 파일을 저장 하는 경우 복합 파일을 사용 하 여 파일 크기 noncompound 파일 보다 훨씬 더 빠르게 증가를 발생할 수 있습니다. 복합 파일 커질 수 있으므로 파일에 저장 하 고 플로피 디스크에서 로드에 대 한 액세스에 적용 될 수, 속도가 느려질 파일입니다.

성능에 영향을 주는 또 다른 문제는 복합 파일의 조각화 합니다. 복합 파일의 크기는 파일에서 사용 하는 첫 번째 및 마지막 디스크 섹터 간의 차이 의해 결정 됩니다. 조각화 된 파일을 공간 데이터를 포함 하지 않습니다 하지만 크기를 계산할 때 계산 되는 많은 영역을 포함할 수 있습니다. 복합 파일의 수명 동안 다양 한이 분야 저장소 개체의 삭제를 삽입 하 여 만들어집니다.

##  <a name="_core_using_compound_files_format_for_your_data"></a> 복합 파일 형식을 사용 하 여 데이터에 대 한

파생 된 문서 클래스에는 응용 프로그램을 성공적으로 만든 후 `COleDocument`, 주 문서 생성자를 호출 하는 확인 `EnableCompoundFile`합니다. 응용 프로그램 OLE 컨테이너 응용 프로그램을 작성 하는 경우이 호출은 삽입 됩니다.

에 *OLE 프로그래머 참조*를 참조 하세요 [IStream](/windows/desktop/api/objidl/nn-objidl-istream), [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage), 및 [ILockBytes](/windows/desktop/api/objidl/nn-objidl-ilockbytes).

## <a name="see-also"></a>참고자료

[컨테이너](../mfc/containers.md)<br/>
[컨테이너: 사용자 인터페이스 문제](../mfc/containers-user-interface-issues.md)<br/>
[COleStreamFile 클래스](../mfc/reference/colestreamfile-class.md)<br/>
[COleDocument 클래스](../mfc/reference/coledocument-class.md)
