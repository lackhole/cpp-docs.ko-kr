---
title: CArchive 개체
ms.date: 11/04/2016
f1_keywords:
- CArchive
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
ms.openlocfilehash: 4bae451168449ce3e120ba9d172a615864ac2157
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346374"
---
# <a name="what-is-a-carchive-object"></a>CArchive 개체

A `CArchive` 쓰거나를 직렬화 가능 개체를 읽기에 대 한 형식이 안전한 버퍼링 메커니즘을 제공 하는 개체를 `CFile` 개체입니다. 일반적으로 `CFile` 개체는 디스크 파일을 나타내며; 단, 메모리 파일을 일 수도 있습니다 (`CSharedFile` 개체), 아마도 클립보드를 나타내는입니다.

지정 된 `CArchive` 중 저장소 개체 (쓰기, serialize) 데이터 또는 로드 (읽기, 역직렬화) 데이터를 되지 둘 다. 기간을 `CArchive` 개체 하나 이상의 통과 개체 파일에 쓰거나 파일에서 개체 읽기로 제한 됩니다. 따라서 연속적으로 만든 두 `CArchive` 파일로 데이터를 직렬화 하 고 다음 파일에서 다시 deserialize 하는 데 필요한 개체입니다.

보관 파일에는 개체에 저장 하는 경우에 보관 파일에 연결 된 `CRuntimeClass` 개체 이름입니다. 그런 다음 다른 보관 파일에서 메모리에 개체를 로드 하는 경우는 `CObject`-파생된 개체에 따라를 동적으로 재생성 됩니다는 `CRuntimeClass` 개체. 보관 파일을 저장 하 여 파일에 기록 된 대로 지정된 된 개체를 두 번 이상 참조할 수 있습니다. 하지만 로드 보관는 개체를 다시 생성 한 번만 합니다. 보관 파일에 연결 하는 방법에 대 한 세부 정보 `CRuntimeClass` 에 설명 된 정보를 개체 및 여러 참조 수를 고려 하는 개체를 다시 만듭니다 [Technical Note 2](../mfc/tn002-persistent-object-data-format.md)합니다.

데이터는 보관으로 serialize 하는 대로 해당 버퍼가 가득 찰 때까지 보관 데이터를 누적 합니다. 다음, 해당 버퍼를 보관 파일에 작성 합니다 `CFile` 가리키는 개체는 `CArchive` 개체입니다. 마찬가지로, 보관 파일에서 데이터를 읽고 나면 데이터를 읽는 버퍼에 파일에서 다음 버퍼 deserialize 된 개체입니다. 이 버퍼링 되므로 응용 프로그램의 성능이 향상 하드 디스크를 읽을 실제로 횟수를 줄입니다.

## <a name="see-also"></a>참고자료

[Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)
