---
title: 'TN002: 영구 개체 데이터 형식'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
ms.openlocfilehash: 6d64799dc17b4b3ddc5c455333b10282e4748b09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306196"
---
# <a name="tn002-persistent-object-data-format"></a>TN002: 영구 개체 데이터 형식

이 지 원하는 영구 MFC 루틴에 설명 합니다 C++ 개체 및 개체 데이터를 파일에 저장 되는 경우의 형식입니다. 이 클래스에만 적용 됩니다는 [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) 하 고 [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로입니다.

## <a name="the-problem"></a>문제

영구 데이터에 대 한 MFC 구현 파일의 단일 인접 부분에 많은 개체에 대 한 데이터를 저장합니다. 개체의 `Serialize` 메서드는 개체의 데이터를 압축 이진 형식으로 변환 합니다.

모든 데이터를 사용 하 여 동일한 형식으로 저장 되는 구현을 보장 합니다 [CArchive 클래스](../mfc/reference/carchive-class.md)합니다. 사용 하 여를 `CArchive` 변환기 개체입니다. 이 개체를 호출 하기 전에 만들어진 시간에서 지속 되 면 [CArchive::Close](../mfc/reference/carchive-class.md#close)합니다. 프로그램을 포함 하는 범위를 종료 될 때 소멸자에서 프로그래머가 명시적으로 또는 암시적으로이 메서드를 호출할 수는 `CArchive`합니다.

이 구현에 설명 합니다 `CArchive` 멤버 [CArchive::ReadObject](../mfc/reference/carchive-class.md#readobject) 하 고 [CArchive::WriteObject](../mfc/reference/carchive-class.md#writeobject)합니다. Arcobj.cpp, 및에 대 한 기본 구현에서 이러한 함수에 대 한 코드를 보면 `CArchive` Arccore.cpp에서. 사용자 코드를 호출 하지 않습니다 `ReadObject` 고 `WriteObject` 직접. 대신, 이러한 개체는 연산자로 클래스 관련 형식이 안전한 삽입 및 추출을 DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로에서 자동으로 생성 되는 사용 됩니다. 다음 코드에서는 어떻게 `WriteObject` 고 `ReadObject` 암시적으로 호출 됩니다.

```
class CMyObject : public CObject
{
    DECLARE_SERIAL(CMyObject)
};

IMPLEMENT_SERIAL(CMyObj, CObject, 1)

// example usage (ar is a CArchive&)
CMyObject* pObj;
CArchive& ar;
ar <<pObj;        // calls ar.WriteObject(pObj)
ar>> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))
```

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>개체 (CArchive::WriteObject) 저장소에 저장

메서드가 `CArchive::WriteObject` 개체를 다시 생성 하는 데 사용 되는 헤더 데이터를 씁니다. 이 데이터는 두 부분으로 구성 됩니다: 개체 유형과 개체의 상태입니다. 이 메서드 (순환 포인터 포함)는 해당 개체에 대 한 포인터의 수에 관계 없이 단일 복사본에만 저장 되도록 작성 중인 개체의 id를 유지 관리를 담당 이기도 합니다.

(삽입)를 저장 하 고 몇 가지 "매니페스트 상수입니다." 사용 (압축 풀기) 개체를 복원 다음은 이진 파일에 저장 되 고 보관 파일 (참고 "w" 접두사를 나타내는 16 비트 수량)에 중요 한 정보를 제공 하는 값입니다.

|태그|설명|
|---------|-----------------|
|wNullTag|NULL 개체 포인터 (0)에 사용 됩니다.|
|wNewClassTag|이 보관 컨텍스트에 (-1) 새 뒤에 오는 클래스 설명을 나타냅니다.|
|wOldClassTag|읽는 중인 개체의 클래스 (0x8000)이 컨텍스트에서 발생을 나타냅니다.|

보관 파일을 유지 하는 개체를 저장할 때를 [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) (합니다 *m_pStoreMap*)는 저장 된 개체에서 32 비트 영구 식별자 (PID)로 매핑. 보관 파일의 컨텍스트에서 저장 되는 모든 고유 클래스 이름과 모든 고유한 개체에 할당 됩니다. 이러한 Pid 아웃 1에서 시작 하는 순차적으로 전달 됩니다. 이러한 Pid는 보관 파일의 범위를 벗어나는 의미가 없습니다 및 특히, 레코드 번호 또는 기타 identity 항목을 사용 하 여 혼동 하면 안 됩니다.

에 `CArchive` 클래스 Pid는 32 비트 이지만 이러한 기록 됩니다 16 비트 0x7FFE 초과 하는 경우가 아니면 합니다. 큰 Pid는 0x7FFF 뒤에 32 비트 PID로 기록 됩니다. 이 이전 버전에서 만든 프로젝트와의 호환성을 유지 합니다.

NULL에 대 한는 검사가 수행 됩니다 (일반적으로 전역 삽입 연산자 사용)가 보관 하는 개체를 저장 하는 요청 이루어지면 [CObject](../mfc/reference/cobject-class.md) 포인터입니다. 포인터가 NULL 인 경우는 *wNullTag* 보관 스트림이에 삽입 됩니다.

포인터가 NULL이 아닌 사용 하는지를 확인 하 고 serialize 할 수 있습니다 (클래스는를 `DECLARE_SERIAL` 클래스), 코드 검사 합니다 *m_pStoreMap* 개체를 이미 저장 된이 있는지 여부를 확인 하려면. 가 있는 경우 코드를 보관 스트림에 해당 개체와 연결 된 32 비트 PID를 삽입 합니다.

이전에 개체를 저장 하지 않았으면 하는 경우 두 가지 방법이 있습니다 고려해 야 할:이 보관 컨텍스트에 새 개체와 개체의 정확한 유형 (즉, 클래스)는 또는 이미 정확한 형식 개체입니다. 형식 나타났습니다 여부를 확인 하려면 코드 쿼리를 *m_pStoreMap* 에 대 한를 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 일치 하는 개체는 `CRuntimeClass` 저장 되는 개체와 연결 된 개체입니다. 일치 하는 항목이 없으면 `WriteObject` 에 대 한 비트는 태그를 삽입 `OR` 의 *wOldClassTag* 및이 인덱스입니다. 경우는 `CRuntimeClass` 보관 컨텍스트에이 새로운 `WriteObject` 클래스에 새 PID를 할당 하 고 앞에, 보관 저장소에 삽입 합니다 *wNewClassTag* 값입니다.

이 클래스에 대 한 설명자를 사용 하 여 보관 삽입 한 다음는 `CRuntimeClass::Store` 메서드. `CRuntimeClass::Store` 스키마 개수 (아래 참조) 클래스 및 클래스의 ASCII 텍스트 이름을 삽입합니다. 참고 ASCII 텍스트 이름 사용 하도록 응용 프로그램에서 보관 파일의 고유성을 보장 하지 않습니다. 따라서 태그를 지정 해야 손상을 방지 하기 위해 데이터 파일. 보관 클래스 정보를 삽입 하는 다음 개체를 배치 합니다 *m_pStoreMap* 를 호출 하는 `Serialize` 클래스 관련 데이터를 삽입 하는 방법입니다. 개체에 배치 합니다 *m_pStoreMap* 호출 하기 전에 `Serialize` 개체의 여러 복사본을 저장소에 저장 되지 않도록 방지 합니다.

초기 호출자 (일반적으로 개체의 네트워크 루트)를 반환 하는 경우 호출 해야 [CArchive::Close](../mfc/reference/carchive-class.md#close)합니다. 다른 수행 하려는 경우 [CFile](../mfc/reference/cfile-class.md)를 호출 해야 작업을 합니다 `CArchive` 메서드 [플러시](../mfc/reference/carchive-class.md#flush) 보관 파일의 손상을 방지 하기 위해.

> [!NOTE]
>  이 구현은 보관 컨텍스트마다 0x3FFFFFFE 인덱스 하드 한도 적용합니다. 이 숫자는 고유 개체 및 클래스는 단일 보관 파일에 저장할 수 있는 최대 수를 나타내지만 단일 디스크 파일을 무제한으로 보관 컨텍스트를 가질 수 있습니다.

## <a name="loading-objects-from-the-store-carchivereadobject"></a>(CArchive::ReadObject) 저장소에서 개체를 로드합니다.

사용 하 여 개체 (압축 풀기)을 로드 합니다 `CArchive::ReadObject` 메서드는 반대로 이며 `WriteObject`. 와 마찬가지로 `WriteObject`, `ReadObject` 사용자 코드에서 직접 호출 되지 않습니다 사용자 코드를 호출 하는 형식이 안전한 추출 연산자를 호출 해야 `ReadObject` 에서 정상적인 `CRuntimeClass`합니다. 이렇게 하면 형식 무결성 추출 작업을 합니다.

있으므로 `WriteObject` 구현 할당 증가 Pid가 1부터 시작 (0 NULL 개체와 미리 정의 된)는 `ReadObject` 구현 보관 컨텍스트의 상태를 유지 하 여 배열을 사용할 수입니다. PID를 읽을 때 저장소에서 PID의 현재 상한 보다 큰 경우 합니다 *m_pLoadArray*, `ReadObject` 새 개체 (또는 클래스 설명) 따름을 알고 있습니다.

## <a name="schema-numbers"></a>스키마 번호

클래스에 할당 되는 스키마 수는 경우는 `IMPLEMENT_SERIAL` 클래스의 메서드는 발견 되는 클래스 구현 "version". 스키마 클래스의 구현을 가리킵니다, 그리고 횟수 필요가 지정된 된 개체가 만들어진 경우에 영구 (일반적으로 개체 버전 이라고 함).

시간이 지남에 따라 동일한 클래스의 여러 구현이 유지 하려는 경우 스키마에 개체를 수정 하는 대로 증가 `Serialize` 메서드 구현을 사용 하면 이전 버전의를 사용 하 여 저장 된 개체를 로드할 수 있는 코드를 작성할 수 있습니다 구현입니다.

합니다 `CArchive::ReadObject` 메서드는 throw를 [CArchiveException](../mfc/reference/carchiveexception-class.md) 메모리에 있는 클래스 설명 스키마 수가 다른 영구 저장소에서 스키마 숫자가 나타날 경우. 이 예외에서 복구 하려면 쉽지 않습니다.

사용할 수 있습니다 `VERSIONABLE_SCHEMA` 함께 (비트 **또는**)이이 예외가 throw 되지 되도록 스키마 버전입니다. 사용 하 여 `VERSIONABLE_SCHEMA`, 코드는 적절 한 조치를 취할 수 해당 `Serialize` 함수에서 반환 된 값을 확인 하 여 [CArchive::GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema)합니다.

## <a name="calling-serialize-directly"></a>호출 직접 Serialize

대부분의 경우 일반 개체 보관 체계의 오버 헤드 `WriteObject` 고 `ReadObject` 필요 하지 않습니다. 이 데이터를 직렬화 하는 작업의 일반적인 경우는 [CDocument](../mfc/reference/cdocument-class.md)합니다. 이 경우에 `Serialize` 메서드는 `CDocument` 추출 또는 삽입 연산자를 사용 하 여 하지를 직접 호출 됩니다. 문서의 내용을 보다 일반적인 개체 보관 구성표를 사용에 될 수 있습니다.

호출 `Serialize` 직접 다음 장점 및 단점을 했습니다.

- 추가 바이트 전에 보관 또는 개체가 serialize 되 면 추가 됩니다. 이 뿐만 아니라 저장된 된 데이터는 작아집니다 있지만를 구현할 수 있도록 `Serialize` 루틴 모든 처리할 수 있는 파일 형식입니다.

- MFC는 조정 하므로 `WriteObject` 및 `ReadObject` 구현과 관련된 컬렉션 연결 되지 않는다는 응용 프로그램에 보다 일반적인 개체 보관 체계를 다른 용도로 필요한 경우가 아니면 합니다.

- 코드는 이전 스키마 숫자에서 복구할 필요가 없습니다. 이렇게 하면 문서 serialization 코드를 인코딩 스키마 번호, 파일 형식 버전 번호 또는 있습니다 숫자 어떤 식별 하는 일을 담당 데이터 파일의 시작 부분에 사용 합니다.

- 직접 호출 하 여 serialize 되는 모든 개체 `Serialize` 사용해 서는 안 `CArchive::GetObjectSchema` 또는 해야 핸들 (단위)-1의 반환 값을 나타내는 버전에서 알 수 없습니다.

때문에 `Serialize` 라고 문서에서 직접 불가능 일반적으로 해당 부모 문서에 대 한 참조를 보관 하려면 문서의 하위 개체에 대 한 합니다. 이러한 개체 해야 포인터가 지정 해당 컨테이너 문서에 명시적으로 또는 사용 해야 합니다 [CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject) 매핑하는 함수는 `CDocument` 이러한 후방 포인터를 보관 하기 전에 PID에 대 한 포인터입니다.

버전 인코드 해야 하며 클래스 정보 직접 호출 하는 경우 앞에서 설명한 대로 `Serialize` 직접 오래 된 파일을 사용 하 여 이전 버전과 호환성을 유지 하면서 형식을 나중에 변경할 수 있도록 합니다. `CArchive::SerializeClass` 함수 직접 개체를 직렬화 또는 기본 클래스를 호출 하기 전에 명시적으로 호출할 수 있습니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
