---
title: accelerator 클래스
ms.date: 11/04/2016
f1_keywords:
- AMPRT/accelerator
- AMPRT/Concurrency::accelerator::accelerator
- AMPRT/Concurrency::accelerator::create_view
- AMPRT/Concurrency::accelerator::get_all
- AMPRT/Concurrency::accelerator::get_auto_selection_view
- AMPRT/Concurrency::accelerator::get_dedicated_memory
- AMPRT/Concurrency::accelerator::get_default_cpu_access_type
- AMPRT/Concurrency::accelerator::get_default_view
- AMPRT/Concurrency::accelerator::get_description
- AMPRT/Concurrency::accelerator::get_device_path
- AMPRT/Concurrency::accelerator::get_has_display
- AMPRT/Concurrency::accelerator::get_is_debug
- AMPRT/Concurrency::accelerator::get_is_emulated
- AMPRT/Concurrency::accelerator::get_supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::get_supports_double_precision
- AMPRT/Concurrency::accelerator::get_supports_limited_double_precision
- AMPRT/Concurrency::accelerator::get_version
- AMPRT/Concurrency::accelerator::set_default
- AMPRT/Concurrency::accelerator::set_default_cpu_access_type
- AMPRT/Concurrency::accelerator::cpu_accelerator
- AMPRT/Concurrency::accelerator::dedicated_memory
- AMPRT/Concurrency::accelerator::default_accelerator
- AMPRT/Concurrency::accelerator::default_cpu_access_type
- AMPRT/Concurrency::accelerator::default_view
- AMPRT/Concurrency::accelerator::description
- AMPRT/Concurrency::accelerator::device_path
- AMPRT/Concurrency::accelerator::direct3d_ref
- AMPRT/Concurrency::accelerator::direct3d_warp
- AMPRT/Concurrency::accelerator::has_display
- AMPRT/Concurrency::accelerator::is_debug
- AMPRT/Concurrency::accelerator::is_emulated
- AMPRT/Concurrency::accelerator::supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::supports_double_precision
- AMPRT/Concurrency::accelerator::supports_limited_double_precision
- AMPRT/Concurrency::accelerator::version
helpviewer_keywords:
- accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
ms.openlocfilehash: 31008b398d17ac0c226f9359745067c4fefc08a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180437"
---
# <a name="accelerator-class"></a>accelerator 클래스

액셀러레이터 키에는 데이터 병렬 계산에 최적화 된 하드웨어 기능입니다. 가속기는 PCIe 버스 (예: GPU)에 연결 된 장치 수 또는 메인 CPU에 설정 된 확장된 명령어를 수 있습니다.

## <a name="syntax"></a>구문

```
class accelerator;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[accelerator 생성자](#ctor)|`accelerator` 클래스의 새 인스턴스를 초기화합니다.|
|[~ accelerator 소멸자](#ctor)|제거 된 `accelerator` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[create_view](#create_view)|만들고 반환을 `accelerator_view` 이 가속기에서 개체입니다.|
|[get_all](#get_all)|벡터를 반환 `accelerator` 가능한 모든 액셀러레이터를 나타내는 개체입니다.|
|[get_auto_selection_view](#get_auto_selection_view)|자동 선택 반환 `accelerator_view`합니다.|
|[get_dedicated_memory](#get_dedicated_memory)|에 대 한 전용된 된 메모리를 반환 합니다 `accelerator`, (킬로바이트)에서.|
|[get_default_cpu_access_type](#get_default_cpu_access_type)|기본 반환 [access_type](concurrency-namespace-enums-amp.md#access_type) 이 가속기에서 만든 버퍼에 대 한 합니다.|
|[get_default_view](#get_default_view)|기본 반환 `accelerator_view` 연관 된 개체는 `accelerator`합니다.|
|[get_description](#get_description)|대 한 간단한 설명을 반환 합니다 `accelerator` 장치입니다.|
|[get_device_path](#get_device_path)|장치의 경로 반환합니다.|
|[get_has_display](#get_has_display)|결정 여부는 `accelerator` 디스플레이에 연결 됩니다.|
|[get_is_debug](#get_is_debug)|결정 여부는 `accelerator` 디버그 레이어를 광범위 한 오류 보고를 위해 사용 했는지입니다.|
|[get_is_emulated](#get_is_emulated)|결정 여부는 `accelerator` 는 캐싱이 에뮬레이트됩니다.|
|[get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|확인 여부는 `accelerator` 공유 메모리 지원|
|[get_supports_double_precision](#get_supports_double_precision)|결정 여부는 `accelerator` 디스플레이에 연결 됩니다.|
|[get_supports_limited_double_precision](#get_supports_limited_double_precision)|확인 여부는 `accelerator` 이중 정밀도 수치를 제한적으로 지원 합니다.|
|[get_version](#get_version)|버전을 반환 합니다 `accelerator`합니다.|
|[set_default](#set_default)|기본 액셀러레이터의 경로 반환 합니다.|
|[set_default_cpu_access_type](#set_default_cpu_access_type)|설정 하는 기본 CPU [access_type](concurrency-namespace-enums-amp.md#access_type)만든 배열 및 암시적 메모리 할당에 대 한 `accelerator`합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator!=](#operator_neq)|비교 `accelerator` 다른 개체를 반환 합니다 **false** 같으면 경우 그렇지 않으면 반환 **true**합니다.|
|[operator=](#operator_eq)|지정 된 내용을 복사 `accelerator` 여기에 개체입니다.|
|[연산자==](#operator_eq_eq)|비교 `accelerator` 다른 개체를 반환 합니다 **true** 같으면 경우 그렇지 않으면 반환 **false**합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[cpu_accelerator](#cpu_accelerator)|CPU에 대 한 상수 문자열을 가져옵니다 `accelerator`합니다.|
|[dedicated_memory](#dedicated_memory)|에 대 한 전용된 된 메모리를 가져옵니다는 `accelerator`, (킬로바이트)에서입니다.|
|[default_accelerator](#default_accelerator)|기본값에 대 한 상수 문자열을 가져옵니다 `accelerator`합니다.|
|[default_cpu_access_type](#default_cpu_access_type)|기본 CPU를 가져오거나 설정 합니다. [access_type](concurrency-namespace-enums-amp.md#access_type)만든 배열 및 암시적 메모리 할당에 대 한 `accelerator`합니다.|
|[default_view](#default_view)|기본값을 가져옵니다 `accelerator_view` 연관 된 개체는 `accelerator`합니다.|
|[description](#description)|대 한 간단한 설명을 가져옵니다는 `accelerator` 장치입니다.|
|[device_path](#device_path)|장치의 경로 가져옵니다.|
|[direct3d_ref](#direct3d_ref)|Direct3D 참조에 대 한 상수 문자열을 가져옵니다 `accelerator`합니다.|
|[direct3d_warp](#direct3d_warp)|문자열에 대 한 상수를 가져옵니다는 `accelerator` 실행 하는 데 사용할 수 있는 개체 C++ (SSE) 사용 하는 다중 코어 Cpu에서 AMP 코드입니다.|
|[has_display](#has_display)|나타내는 부울 값을 가져옵니다 여부를 `accelerator` 디스플레이에 연결 됩니다.|
|[is_debug](#is_debug)|나타냅니다 여부는 `accelerator` 디버그 레이어를 광범위 한 오류 보고를 위해 사용 했는지입니다.|
|[is_emulated](#is_emulated)|나타냅니다 여부는 `accelerator` 는 캐싱이 에뮬레이트됩니다.|
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|나타냅니다 여부는 `accelerator` 공유 메모리를 지원 합니다.|
|[supports_double_precision](#supports_double_precision)|액셀러레이터가 이중 정밀도 수치를 지원 하는지 여부를 나타냅니다.|
|[supports_limited_double_precision](#supports_limited_double_precision)|액셀러레이터 키 이중 정밀도 수치에 대 한 지원이 제한적 여부를 나타냅니다.|
|[version](#version)|버전을 가져옵니다는 `accelerator`합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`accelerator`

## <a name="remarks"></a>설명

액셀러레이터 키에는 데이터 병렬 계산에 최적화 된 하드웨어 기능입니다. 액셀러레이터는 종종 개별 GPU 이지만 DirectX REF 장치, WARP (sse를 사용 하 여 가속 됩니다 CPU 측 장치)에서는 또는 CPU 자체 같은 가상 호스트 측 엔터티가 될 수도 있습니다.

생성할 수 있습니다는 `accelerator` 가능한 장치를 열거 하거나 기본 장치, 참조 장치 또는 WARP 장치를 가져와서 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** amprt.h

**네임스페이스:** 동시성

##  <a name="dtor"></a> </a> ~accelerator

제거 된 `accelerator` 개체입니다.

```
~accelerator();
```

### <a name="return-value"></a>반환 값

##  <a name="ctor"></a> 액셀러레이터 키

새 인스턴스를 초기화 합니다 [가속기 클래스](accelerator-class.md)합니다.

```
accelerator();

explicit accelerator(const std::wstring& _Device_path);

accelerator(const accelerator& _Other);
```

### <a name="parameters"></a>매개 변수

*_Device_path*<br/>
물리적 장치의 경로입니다.

*_Other*<br/>
복사할 액셀러레이터 키입니다.

##  <a name="cpu_accelerator"></a> cpu_accelerator

CPU 엑셀러레이터에 대한 문자열 상수를 가져옵니다.

```
static const wchar_t cpu_accelerator[];
```

##  <a name="create_view"></a> create_view

지정된 큐 모드를 사용하여 이 액셀러레이터에서 `accelerator_view` 개체를 만들고 반환합니다. 큐 모드가 지정 되지 않은 경우, 새 `accelerator_view` 사용 하는 [queuing_mode:: immediate](concurrency-namespace-enums-amp.md#queuing_mode) 큐 모드입니다.

```
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>매개 변수

*qmode*<br/>
큐 모드입니다.

### <a name="return-value"></a>반환 값

지정된 큐 모드를 사용하는 이 액셀러레이터의 새로운 `accelerator_view` 개체입니다.

##  <a name="dedicated_memory"></a> dedicated_memory

에 대 한 전용된 된 메모리를 가져옵니다는 `accelerator`, (킬로바이트)에서입니다.

```
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;
```

##  <a name="default_accelerator"></a> default_accelerator

기본값에 대 한 상수 문자열을 가져옵니다 `accelerator`합니다.

```
static const wchar_t default_accelerator[];
```

##  <a name="default_cpu_access_type"></a> default_cpu_access_type

기본 cpu [access_type](concurrency-namespace-enums-amp.md#access_type)만든 배열 및 암시적 메모리 할당에 대 한 `accelerator`합니다.

```
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;
```

##  <a name="default_view"></a> default_view

연결 된 기본 액셀러레이터 보기를 가져옵니다는 `accelerator`합니다.

```
__declspec(property(get= get_default_view)) accelerator_view default_view;
```

##  <a name="description"></a> description

대 한 간단한 설명을 가져옵니다는 `accelerator` 장치입니다.

```
__declspec(property(get= get_description)) std::wstring description;
```

##  <a name="device_path"></a> device_path

액셀러레이터의 경로를 가져옵니다. 이 경로는 시스템에서 고유합니다.

```
__declspec(property(get= get_device_path)) std::wstring device_path;
```

##  <a name="direct3d_ref"></a> direct3d_ref

Direct3D 참조 엑셀러레이터에 대한 문자열 상수를 가져옵니다.

```
static const wchar_t direct3d_ref[];
```

##  <a name="direct3d_warp"></a> direct3d_warp

문자열에 대 한 상수를 가져옵니다는 `accelerator` 실행 하는 데 사용할 수 있는 개체에 C++ (SSE)를 사용 하 여 다중 코어 Cpu에서 AMP 코드입니다.

```
static const wchar_t direct3d_warp[];
```

##  <a name="get_all"></a> get_all

벡터를 반환 `accelerator` 가능한 모든 액셀러레이터를 나타내는 개체입니다.

```
static inline std::vector<accelerator> get_all();
```

### <a name="return-value"></a>반환 값

사용할 수 있는 액셀러레이터의 벡터

##  <a name="get_auto_selection_view"></a> get_auto_selection_view

자동 선택 accelerator_view를 반환 합니다. 경우에는 런타임에 의해 자동으로 선택할 parallel_for_each를 실행 하기 위해 대상 accelerator_view에서 parallel_for_each 대상 결과로 지정 합니다. 다른 모든 목적으로 accelerator_view이 메서드에서 반환 되는 기본 액셀러레이터의 기본 accelerator_view와 동일

```
static accelerator_view __cdecl get_auto_selection_view();
```

### <a name="return-value"></a>반환 값

자동 선택 accelerator_view입니다.

##  <a name="get_dedicated_memory"></a> get_dedicated_memory

에 대 한 전용된 된 메모리를 반환 합니다 `accelerator`, (킬로바이트)에서.

```
size_t get_dedicated_memory() const;
```

### <a name="return-value"></a>반환 값

`accelerator`를 위해 전용된 메모리(킬로바이트)입니다.

##  <a name="get_default_cpu_access_type"></a> get_default_cpu_access_type

이 가속기에서 만든 버퍼에 대 한 기본 cpu access_type을 가져옵니다.

```
access_type get_default_cpu_access_type() const;
```

### <a name="return-value"></a>반환 값

이 가속기에서 만든 버퍼에 대 한 기본 cpu access_type 합니다.

##  <a name="get_default_view"></a> get_default_view

기본 반환 `accelerator_view` 연관 된 개체는 `accelerator`합니다.

```
accelerator_view get_default_view() const;
```

### <a name="return-value"></a>반환 값

`accelerator_view`와 연결된 기본 `accelerator` 개체입니다.

##  <a name="get_description"></a> get_description

대 한 간단한 설명을 반환 합니다 `accelerator` 장치입니다.

```
std::wstring get_description() const;
```

### <a name="return-value"></a>반환 값

`accelerator` 장치에 대한 간단한 설명입니다.

##  <a name="get_device_path"></a> get_device_path

액셀러레이터의 경로 반환 합니다. 이 경로는 시스템에서 고유합니다.

```
std::wstring get_device_path() const;
```

### <a name="return-value"></a>반환 값

시스템 차원의 고유 장치 인스턴스 경로입니다.

##  <a name="get_has_display"></a> get_has_display

나타내는 부울 값을 반환 하는지 여부를 `accelerator` 디스플레이에 출력할 수 있습니다.

```
bool get_has_display() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 경우는 `accelerator` ; 디스플레이에 출력할 수이 고, 그렇지 **false**합니다.

##  <a name="get_is_debug"></a> get_is_debug

결정 여부는 `accelerator` 디버그 레이어를 광범위 한 오류 보고를 위해 사용 했는지입니다.

```
bool get_is_debug() const;
```

### <a name="return-value"></a>반환 값

**true** 경우는 `accelerator` 를 위해 DEBUG 레이어가 활성화 폭넓은 오류 보고 했습니다. 그렇지 않으면 **false**합니다.

##  <a name="get_is_emulated"></a> get_is_emulated

결정 여부는 `accelerator` 는 캐싱이 에뮬레이트됩니다.

```
bool get_is_emulated() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 경우는 `accelerator` 는 캐싱이 에뮬레이트됩니다. 그렇지 않으면 **false**합니다.

##  <a name="get_supports_cpu_shared_memory"></a> get_supports_cpu_shared_memory

액셀러레이터가 액셀러레이터 및 CPU에서 모두 액세스할 수 있는 메모리 지원 여부를 나타내는 부울 값을 반환 합니다.

```
bool get_supports_cpu_shared_memory() const;
```

### <a name="return-value"></a>반환 값

**true 이면** accelerator에서 지 원하는 CPU 메모리를 공유 하는 경우이 고, 그렇지 **false**합니다.

##  <a name="get_supports_double_precision"></a> get_supports_double_precision

액셀러레이터가 이중 정밀도 수치를 지원 합니다 있는지 여부를 포함 하 여 결합 하는 여부를 나타내는 부울 값을 곱하기 반환 추가 (FMA), 나누기, 역 수 및 사이의 캐스팅 **int** 및 **double**

```
bool get_supports_double_precision() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 액셀러레이터가 이중 정밀도 수치; 지원 되는 경우이 고, 그렇지 **false**합니다.

##  <a name="get_supports_limited_double_precision"></a> get_supports_limited_double_precision

액셀러레이터가 이중 정밀도 수치를 제한적으로 지원하는지 여부를 나타내는 부울 값을 반환합니다. 액셀러레이터 키에만 제한적으로 지원, fused multiply (FMA)를 추가 하는 경우 나누기, 역 수 및 사이의 캐스팅 **int** 하 고 **double** 지원 되지 않습니다.

```
bool get_supports_limited_double_precision() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 액셀러레이터에 이중 정밀도 수치;에 대 한 지원 제한 되어 있으면이 고, 그렇지 **false**합니다.

##  <a name="get_version"></a> get_version

버전을 반환 합니다 `accelerator`합니다.

```
unsigned int get_version() const;
```

### <a name="return-value"></a>반환 값

버전을 `accelerator`입니다.

##  <a name="has_display"></a> has_display

나타내는 부울 값을 가져옵니다 여부는 `accelerator` 디스플레이에 출력할 수 있습니다.

```
__declspec(property(get= get_has_display)) bool has_display;
```

##  <a name="is_debug"></a> is_debug

나타내는 부울 값을 가져옵니다 여부는 `accelerator` 디버그 레이어를 광범위 한 오류 보고를 위해 사용 했는지입니다.

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

##  <a name="is_emulated"></a> is_emulated

나타내는 부울 값을 가져옵니다 여부는 `accelerator` 는 캐싱이 에뮬레이트됩니다.

```
__declspec(property(get= get_is_emulated)) bool is_emulated;
```

##  <a name="operator_neq"></a> operator!=

비교 `accelerator` 다른 개체를 반환 합니다 **false** 같으면 경우 그렇지 않으면 반환 **true**합니다.

```
bool operator!= (const accelerator& _Other) const;
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
이것과 비교할 `accelerator` 개체입니다.

### <a name="return-value"></a>반환 값

**false** 하는 경우 두 `accelerator` 개체가 동일한 지 고, 그렇지 않으면 **true**합니다.

##  <a name="operator_eq"></a> operator=

지정 된 내용을 복사 `accelerator` 여기에 개체입니다.

```
accelerator& operator= (const accelerator& _Other);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`accelerator` 복사할 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `accelerator` 개체입니다.

##  <a name="operator_eq_eq"></a> operator==

비교 `accelerator` 다른 개체를 반환 합니다 **true** 같으면 경우 그렇지 않으면 반환 **false**합니다.

```
bool operator== (const accelerator& _Other) const;
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
이것과 비교할 `accelerator` 개체입니다.

### <a name="return-value"></a>반환 값

**true** 하는 경우 다른 `accelerator` 개체가이 동일 `accelerator` ; 개체이 고, 그렇지 **false**합니다.

##  <a name="set_default"></a> set_default

암시적으로 기본 액셀러레이터를 사용 하는 모든 작업에 사용할 기본 액셀러레이터를 설정 합니다. 이 메서드는 런타임에서 선택한 기본 액셀러레이터가 기본 액셀러레이터를 암시적으로 사용 하는 작업에서 이미 사용 되지 않은 경우에 성공

```
static inline bool set_default(std::wstring _Path);
```

### <a name="parameters"></a>매개 변수

*_Path*<br/>
액셀러레이터 키에 대 한 경로입니다.

### <a name="return-value"></a>반환 값

**true** 기본 액셀러레이터 설정 시 호출이 성공 하는 경우. 그렇지 않으면 **false**합니다.

##  <a name="set_default_cpu_access_type"></a> set_default_cpu_access_type

이 가속기에서 액세스 하는 array_views의 일부로 암시적 메모리 할당 또는이 액셀러레이터에서 만든 배열에 대 한 기본 cpu access_type을 설정 합니다. 이 메서드는 런타임에서 선택한 default_cpu_access_type이이 가속기에 대 한 사용 되지 않은 아직 또는 배열을 할당 하는 것에 대 한 액셀러레이터의 default_cpu_access_type가 아직이 메서드에 대 한 이전 호출에서 재정의 된 경우에 성공 이 가속기에서 액세스 된 array_view를 백업 하는 암시적 메모리 할당 합니다.

```
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```

### <a name="parameters"></a>매개 변수

*_Default_cpu_access_type*<br/>
이 가속기에서 배열/array_view 메모리 할당에 사용할 기본 cpu access_type 합니다.

### <a name="return-value"></a>반환 값

액셀러레이터 키에 대 한 기본 cpu access_type이 성공적으로 설정 하는 경우를 나타내는 부울 값입니다.

##  <a name="supports_cpu_shared_memory"></a> supports_cpu_shared_memory

나타내는 부울 값을 가져옵니다 여부는 `accelerator` 공유 메모리를 지원 합니다.

```
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;
```

##  <a name="supports_double_precision"></a> supports_double_precision

액셀러레이터가 배정밀도 수치를 지원하는지 여부를 나타내는 부울 값을 가져옵니다.

```
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;
```

##  <a name="supports_limited_double_precision"></a> supports_limited_double_precision

액셀러레이터 키 이중 정밀도 수치에 대 한 지원이 제한적 여부를 나타내는 부울 값을 가져옵니다. 액셀러레이터에서 제한적으로만 지원하는 경우 FMA(Fused Multiply Add), 나누기, 역수 및 `int` 및 `double` 사이의 캐스팅은 지원되지 않습니다.

```
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;
```

##  <a name="version"></a> 버전

버전을 가져옵니다는 `accelerator`합니다.

```
__declspec(property(get= get_version)) unsigned int version;
```

##  <a name="dtor"></a> </a> ~accelerator_view

제거 된 [accelerator_view](accelerator-view-class.md) 개체입니다.

```
~accelerator_view();
```

### <a name="return-value"></a>반환 값

##  <a name="accelerator"></a> 액셀러레이터 키

가져옵니다 합니다 `accelerator` 개체를 [accelerator_view](accelerator-view-class.md) 개체입니다.

```
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

##  <a name="ctor"></a> accelerator_view

새 인스턴스를 초기화 합니다 [accelerator_view](accelerator-view-class.md) 기존 복사 하 여 클래스 `accelerator_view` 개체입니다.

```
accelerator_view(const accelerator_view& _Other);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`accelerator_view` 복사할 개체입니다.

##  <a name="create_marker"></a> create_marker

지금이 전송 된 모든 명령의 완료를 추적 하는 future를 반환 `accelerator_view` 개체입니다.

```
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>반환 값

지금이 전송 된 모든 명령의 완료를 추적 하는 미래 `accelerator_view` 개체입니다.

##  <a name="flush"></a> flush

모든 보류 중인 명령은 큐에 대기 중인 전송 합니다 [accelerator_view](accelerator-view-class.md) 실행에 대 한 액셀러레이터 키에는 개체입니다.

```
void flush();
```

### <a name="return-value"></a>반환 값

`void`를 반환합니다.

##  <a name="get_accelerator"></a> get_accelerator

반환 된 `accelerator` 개체에 대 한 합니다 [accelerator_view](accelerator-view-class.md) 개체입니다.

```
accelerator get_accelerator() const;
```

### <a name="return-value"></a>반환 값

합니다 `accelerator` 개체는 `accelerator_view` 개체입니다.

##  <a name="get_is_auto_selection"></a> get_is_auto_selection

선택할지 여부를 자동으로 적절 한 액셀러레이터 accelerator_view 전달 될 때를 나타내는 부울 값을 반환 된 [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each)합니다.

```
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 런타임에서 자동으로 적절 한 액셀러레이터;를 선택 하는 경우이 고, 그렇지 **false**합니다.

##  <a name="get_is_debug"></a> get_is_debug

나타내는 부울 값을 반환 하는지 여부를 [accelerator_view](accelerator-view-class.md) 개체를 위해 DEBUG 레이어가 활성화 폭넓은 오류 보고에 있습니다.

```
bool get_is_debug() const;
```

### <a name="return-value"></a>반환 값

`accelerator_view` 개체에 확장 오류 보고를 위해 DEBUG 레이어가 활성화되었는지 여부를 나타내는 부울 값입니다.

##  <a name="get_queuing_mode"></a> get_queuing_mode

큐 모드를 반환 합니다 [accelerator_view](accelerator-view-class.md) 개체입니다.

```
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>반환 값

`accelerator_view` 개체의 큐 모드입니다.

##  <a name="get_version"></a> get_version

버전을 반환 합니다 [accelerator_view](accelerator-view-class.md)합니다.

```
unsigned int get_version() const;
```

### <a name="return-value"></a>반환 값

버전을 `accelerator_view`입니다.

##  <a name="is_auto_selection"></a> is_auto_selection

선택할지 여부를 자동으로 적절 한 액셀러레이터 accelerator_view 전달 될 때를 나타내는 부울 값을 가져옵니다를 [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each)합니다.

```
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

##  <a name="is_debug"></a> is_debug

나타내는 부울 값을 가져옵니다 여부는 [accelerator_view](accelerator-view-class.md) 개체를 위해 DEBUG 레이어가 활성화 폭넓은 오류 보고에 합니다.

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

##  <a name="operator_neq"></a> operator!=

비교 [accelerator_view](accelerator-view-class.md) 다른 개체를 반환 합니다 `false` 같으면 경우 그렇지 않으면 반환 `true`합니다.

```
bool operator!= (const accelerator_view& _Other) const;
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
이것과 비교할 `accelerator_view` 개체입니다.

### <a name="return-value"></a>반환 값

**false** 두 개체가 동일 하면이 고, 그렇지 **true**합니다.

##  <a name="operator_eq"></a> operator=

지정 된 콘텐츠를 복사 [accelerator_view](accelerator-view-class.md) 을 여기에 개체입니다.

```
accelerator_view& operator= (const accelerator_view& _Other);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`accelerator_view` 복사할 개체입니다.

### <a name="return-value"></a>반환 값

수정된 `accelerator_view` 개체에 대한 참조입니다.

##  <a name="operator_eq_eq"></a> operator==

비교 [accelerator_view](accelerator-view-class.md) 다른 개체를 반환 합니다 **true** 같으면 경우 그렇지 않으면 반환 **false**합니다.

```
bool operator== (const accelerator_view& _Other) const;
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
이것과 비교할 `accelerator_view` 개체입니다.

### <a name="return-value"></a>반환 값

**true 이면** 두 개체가 동일 하면이 고, 그렇지 **false**합니다.

##  <a name="queuing_mode"></a> queuing_mode

큐 모드를 가져옵니다 합니다 [accelerator_view](accelerator-view-class.md) 개체입니다.

```
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

##  <a name="version"></a> 버전

버전을 가져옵니다 합니다 [accelerator_view](accelerator-view-class.md)합니다.

```
__declspec(property(get= get_version)) unsigned int version;
```

##  <a name="wait"></a> 대기

모든 명령에 제출 될 때까지 대기 합니다 [accelerator_view](accelerator-view-class.md) 개체가 완료 합니다.

```
void wait();
```

### <a name="return-value"></a>반환 값

`void`를 반환합니다.

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
