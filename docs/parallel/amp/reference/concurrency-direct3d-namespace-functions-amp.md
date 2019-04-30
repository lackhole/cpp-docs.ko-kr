---
title: Concurrency::direct3d 네임 스페이스 함수 (AMP)
ms.date: 08/31/2018
f1_keywords:
- amp/Concurrency::direct3d::abs
- amp/Concurrency::direct3d::countbits
- amp/Concurrency::direct3d::create_accelerator_view
- amp/Concurrency::direct3d::d3d_access_lock
- amp/Concurrency::direct3d::d3d_access_unlock
- amp/Concurrency::direct3d::firstbithigh
- amp/Concurrency::direct3d::get_buffer
- amp/Concurrency::direct3d::get_device
- amp/Concurrency::direct3d::imax
- amp/Concurrency::direct3d::is_timeout_disabled
- amp/Concurrency::direct3d::mad
- amp/Concurrency::direct3d::noise
- amp/Concurrency::direct3d::radians
- amp/Concurrency::direct3d::reversebits
- amp/Concurrency::direct3d::saturate
- amp/Concurrency::direct3d::smoothstep
- amp/Concurrency::direct3d::step
- amp/Concurrency::direct3d::umin
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
ms.openlocfilehash: 0a2977faf094aafb6290063e39e062ffaeaaec81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405588"
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Concurrency::direct3d 네임 스페이스 함수 (AMP)

||||
|-|-|-|
|[abs](#abs)|[clamp](#clamp)|[countbits](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|[d3d_access_lock](#d3d_access_lock)||
|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|[firstbithigh](#firstbithigh)|
|[firstbitlow](#firstbitlow)|[get_buffer](#get_buffer)|[get_device](#get_device)|
|[imax](#imax)|[imin](#imin)|[is_timeout_disabled](#is_timeout_disabled)|
|[mad](#mad)|[make_array](#make_array)|[noise](#noise)|
|[radians](#radians)|[rcp](#rcp)|[reversebits](#reversebits)|
|[saturate](#saturate)|[sign](#sign)|[smoothstep](#smoothstep)|
|[step](#step)|[umax](#umax)|[umin](#umin)|

## <a name="requirements"></a>요구 사항

**헤더:** amp.h **Namespace:** 동시성

##  <a name="abs"></a>  abs

인수의 절대값을 반환 합니다.

```
inline int abs(int _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
정수 값

### <a name="return-value"></a>반환 값

인수의 절대값을 반환합니다.

##  <a name="clamp"></a>  clamp

지정된 된 두 번째 및 세 번째 인수를 정의한 범위에 고정 하는 첫 번째 지정 된 인수의 값을 계산 합니다.

```
inline float clamp(
    float _X,
    float _Min,
    float _Max) restrict(amp);

inline int clamp(
    int _X,
    int _Min,
    int _Max) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
고정 값

*_Min*<br/>
고정 범위의 하한값입니다.

*_Max*<br/>
고정 범위의 상한입니다.

### <a name="return-value"></a>반환 값

고정 된 값 `_X`합니다.

##  <a name="countbits"></a>  countbits

_X에서 설정 비트의 개수

```
inline unsigned int countbits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
부호 없는 정수 값

### <a name="return-value"></a>반환 값

_X에서 설정 비트의 수를 반환합니다.

## <a name="create_accelerator_view"></a> create_accelerator_view

만듭니다는 [accelerator_view](accelerator-view-class.md) 개체에 대 한 포인터에서 Direct3D 장치 인터페이스입니다.

## <a name="syntax"></a>구문

```
accelerator_view create_accelerator_view(
    IUnknown * _D3D_device
    queuing_mode _Qmode = queuing_mode_automatic);

accelerator_view create_accelerator_view(
    accelerator& _Accelerator,
    bool _Disable_timeout
    queuing_mode _Qmode = queuing_mode_automatic);
```

#### <a name="parameters"></a>매개 변수

*_Accelerator*<br/>
새 accelerator_view를 만들려는 액셀러레이터입니다.

*_D3D_device*<br/>
Direct3D 장치 인터페이스에 대 한 포인터입니다.

*_Disable_timeout*<br/>
새로 만든된 accelerator_view에 대 한 제한 시간을 비활성화 해야 하는지 여부를 지정 하는 부울 매개 변수입니다. Direct3D 장치를 만들기 위한 D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT 플래그에 해당 하 고 운영 체제 Windows 제한 시간 별로 장치를 재설정 하지 않고 실행 하는 데 2 초 이상 걸리는 작업을 허용 해야 하는 경우를 나타내는 데이 감지 및 복구 메커니즘입니다. Accelerator_view에서 시간이 오래 걸리는 작업을 수행 해야 하는 경우이 플래그의 사용을 사용 하는 것이 좋습니다.

*_Qmode*<br/>
합니다 [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) 새로 만든된 accelerator_view에 대해 사용할 수 있습니다. 이 매개 변수는 기본값은 `queuing_mode_automatic`합니다.

## <a name="return-value"></a>반환 값

`accelerator_view` 전달 된 Direct3D 장치 인터페이스에서 생성 된 개체입니다.

## <a name="remarks"></a>설명

이 함수에서는 새 `accelerator_view` 개체 기존 포인터에서 Direct3D 장치 인터페이스입니다. 함수 호출에 성공 하면 참조 횟수 매개 변수는 이용 하 여 증가 `AddRef` 인터페이스를 호출 합니다. DirectX 코드에 더 이상 필요한 경우 개체를 안전 하 게 릴리스할 수 없습니다. 메서드 호출에 실패 하는 경우는 [runtime_exception](runtime-exception-class.md) throw 됩니다.

`accelerator_view` 이 함수를 사용 하 여 만든 개체는 스레드로부터 안전 합니다. 동시 사용을 동기화 해야 합니다는 `accelerator_view` 개체입니다. 동시 사용을 `accelerator_view` 개체 및 원시 ID3D11Device 인터페이스 정의 되지 않은 동작이 발생 합니다.

C++ AMP 런타임이 사용 하는 경우 D3D 디버그 레이어를 사용 하 여 디버그 모드에서 자세한 오류 정보를 제공 합니다 `D3D11_CREATE_DEVICE_DEBUG` 플래그입니다.

##  <a name="d3d_access_lock"></a>  d3d_access_lock

Accelerator_view와 공유 되는 리소스에서 D3D 작업을 안전 하 게 수행할 목적으로 accelerator_view에 대 한 잠금을 획득 합니다. Accelerator_view와 모든 C++ 내부적으로 액셀러레이터이 뷰와 연관 AMP 리소스 잠금을이 작업을 수행할 때 다른 스레드가 D3D 액세스 잠금을 보유 하는 동안 차단 됩니다. 이 잠금은 비재귀적 같습니다. 스레드에서 이미 잠금을 보유 하는이 함수를 호출 하는 정의 되지 않은 동작은 합니다. Accelerator_view 또는 D3D 액세스 잠금을 보유 하는 스레드의 accelerator_view와 연결 된 모든 데이터 컨테이너에 대 한 작업을 수행 하는 정의 되지 않은 동작은 합니다. 범위 기반 D3D 액세스 잠금에 대 한 한 RAII 스타일 클래스인 scoped_d3d_access_lock도 참조 하세요.

```
void __cdecl d3d_access_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>매개 변수

*_Av*<br/>
잠글 accelerator_view입니다.

##  <a name="d3d_access_try_lock"></a>  d3d_access_try_lock

차단 하지 않고 accelerator_view에 대 한 D3D 액세스 잠금을 획득 하려고 시도 합니다.

```
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>매개 변수

*_Av*<br/>
잠글 accelerator_view입니다.

### <a name="return-value"></a>반환 값

잠금을 획득 하는 경우 true 또는 false 다른 스레드에 의해 현재 보유 하는 경우입니다.

##  <a name="d3d_access_unlock"></a>  d3d_access_unlock

제공된 된 accelerator_view에 대 한 D3D 액세스 잠금 릴리스 합니다. 호출 스레드가 accelerator_view에서 잠금을 유지 하지 않으면 결과가 정의 되지 않습니다.

```
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```

### <a name="parameters"></a>매개 변수

*_Av*<br/>
잠금을 발표를 앞둔 accelerator_view입니다.

##  <a name="firstbithigh"></a>  firstbithigh

가장 높은 순위의 비트부터 가장 낮은 순위의 비트 쪽으로 이동 하 여 _x에서 첫 번째 설정 비트의 위치를 가져옵니다.

```
inline int firstbithigh(int _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
정수 값

### <a name="return-value"></a>반환 값

첫 번째 설정 비트의 위치

##  <a name="firstbitlow"></a>  firstbitlow

최하위 비트를 사용 하 여 시작 가장 높은 순위의 비트 쪽으로 작업 하 여 _x에서 첫 번째 설정 비트의 위치를 가져옵니다.

```
inline int firstbitlow(int _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
정수 값

### <a name="return-value"></a>반환 값

첫 번째 설정 비트의 위치를 반환 합니다.

##  <a name="get_buffer"></a>  get_buffer

지정된 된 배열의 내부 Direct3D 버퍼 인터페이스를 가져옵니다.

```
template<
    typename value_type,
    int _Rank
>
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;
```

### <a name="parameters"></a>매개 변수

*value_type*<br/>
배열 요소의 형식입니다.

*_Rank*<br/>
배열의 차수입니다.

*_Array*<br/>
기본 Direct3D 버퍼 인터페이스를 반환 되는 Direct3D accelerator_view의 배열입니다.

### <a name="return-value"></a>반환 값

배열의 내부 Direct3D 버퍼에 해당 하는 IUnknown 인터페이스 포인터입니다.

## <a name="a-namegetdevice-getdevice"></a><a name="get_device"> get_device

Accelerator_view는 내부 D3D 장치 인터페이스를 가져옵니다.

```
IUnknown* get_device(const accelerator_view Av);
```

### <a name="parameters"></a>매개 변수

*Av*<br/>
기본 D3D 장치 인터페이스가 반환 되는 D3D accelerator_view입니다.

### <a name="return-value"></a>반환 값

`IUnknown` accelerator_view 기본 D3D 장치 인터페이스 포인터입니다.

##  <a name="imax"></a>  imax

인수의 최대 숫자 값을 확인

```
inline int imax(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
정수 값

*_Y*<br/>
정수 값

### <a name="return-value"></a>반환 값

인수의 최대 숫자 값을 반환 합니다.

##  <a name="imin"></a>  imin

인수의 최소 숫자 값을 확인

```
inline int imin(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
정수 값

*_Y*<br/>
정수 값

### <a name="return-value"></a>반환 값

인수의 최소 숫자 값을 반환 합니다.

##  <a name="is_timeout_disabled"></a>  is_timeout_disabled

지정된 된 accelerator_view에 대 한 제한 시간이 비활성화 되었는지 하는 경우를 나타내는 부울 플래그를 반환 합니다. 이 Direct3D 장치를 만들기 위한 D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT 플래그에 해당합니다.

```
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```

### <a name="parameters"></a>매개 변수

*_Accelerator_view*<br/>
제한 시간 설정을 비활성화 있는 accelerator_view를 쿼리할 수 됩니다.

### <a name="return-value"></a>반환 값

지정된 된 accelerator_view에 대 한 제한 시간이 비활성화 되었는지 하는 경우를 나타내는 부울 플래그입니다.

##  <a name="mad"></a>  mad

첫 번째와 두 번째 지정 된 인수의 곱을 세 번째 지정 된 인수를 추가 합니다.

```
inline float mad(
    float _X,
    float _Y,
    float _Z) restrict(amp);

inline double mad(
    double _X,
    double _Y,
    double _Z) restrict(amp);

inline int mad(
    int _X,
    int _Y,
    int _Z) restrict(amp);

inline unsigned int mad(
    unsigned int _X,
    unsigned int _Y,
    unsigned int _Z) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
첫 번째 인수를 지정 합니다.

*_Y*<br/>
두 번째 인수를 지정 합니다.

*_Z*<br/>
세 번째 인수를 지정 합니다.

### <a name="return-value"></a>반환 값

결과인 `_X` \* `_Y`  +  `_Z`합니다.

##  <a name="make_array"></a>  make_array

Direct3D 버퍼 인터페이스 포인터에서 배열을 만듭니다.

```
template<
    typename value_type,
    int _Rank
>
array<value_type, _Rank> make_array(
    const extent<_Rank>& _Extent,
    const Concurrency::accelerator_view& _Rv,
    IUnknown* _D3D_buffer)  ;
```

### <a name="parameters"></a>매개 변수

*value_type*<br/>
만들려는 배열의 요소 형식입니다.

*_Rank*<br/>
만들려는 배열의 차수입니다.

*_Extent*<br/>
배열 집합체의 모양을 설명 하는 범위입니다.

*_Rv*<br/>
배열이 만들 D3D 액셀러레이터 보기입니다.

*_D3D_buffer*<br/>
배열을 만들기 위한 D3D 버퍼의 IUnknown 인터페이스 포인터입니다.

### <a name="return-value"></a>반환 값

제공 된 Direct3D 버퍼를 사용 하 여 만든 배열입니다.

##  <a name="noise"></a>  noise

Perlin 노이즈 알고리즘을 사용하여 임의의 값을 생성합니다.

```
inline float noise(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
Perlin 노이즈를 생성하는 부동 소수점 값

### <a name="return-value"></a>반환 값

-1과 1 사이의 범위 내에서 Perlin 노이즈 값을 반환합니다.

##  <a name="radians"></a>  radians

_X 각도에서 라디안으로 변환

```
inline float radians(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
부동 소수점 값

### <a name="return-value"></a>반환 값

각도에서 라디안으로 변환한 _X를 반환합니다.

##  <a name="rcp"></a>  rcp

빠른 근사값을 사용 하 여 지정 된 인수의 역 수를 계산 합니다.

```
inline float rcp(float _X) restrict(amp);

inline double rcp(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
역 수를 계산 하는 값입니다.

### <a name="return-value"></a>반환 값

지정 된 인수의 역 수입니다.

##  <a name="reversebits"></a>  reversebits

_X의 비트 순서를 반대로 바꿉니다.

```
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
부호 없는 정수 값

### <a name="return-value"></a>반환 값

_X의 반대로 바뀐 비트 순서 값을 반환합니다.

##  <a name="saturate"></a>  saturate

0 ~ 1의 범위 내에서 _X 범위로 제한

```
inline float saturate(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
부동 소수점 값

### <a name="return-value"></a>반환 값

0 - 1의 범위 내로 제한된 _X를 반환합니다.

##  <a name="sign"></a>  sign

지정 된 인수의 부호를 결정합니다.

```
inline int sign(int _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
정수 값

### <a name="return-value"></a>반환 값

인수의 기호입니다.

##  <a name="smoothstep"></a>  smoothstep

_X가 [_Min, _Max] 범위에 있으면 0과 1 사이의 부드러운 Hermite 보간을 반환 합니다.

```
inline float smoothstep(
    float _Min,
    float _Max,
    float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Min*<br/>
부동 소수점 값

*_Max*<br/>
부동 소수점 값

*_X*<br/>
부동 소수점 값

### <a name="return-value"></a>반환 값

_X가 _Min보다 작은 경우 0을, _X가 _Max보다 큰 경우 1을 반환합니다. 그렇지 않으면, _X가 [_Min, _Max] 범위에 있는 경우 0과 1 사이의 값입니다.

##  <a name="step"></a>  step

더 큰 값에 기반한 0 또는 1을 반환 하는 두 값을 비교

```
inline float step(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Y*<br/>
부동 소수점 값

*_X*<br/>
부동 소수점 값

### <a name="return-value"></a>반환 값

_X가 _Y보다 큰 경우 1을 반환합니다. 그렇지 않으면, 0을 반환합니다.

##  <a name="umax"></a>  umax

인수의 최대 숫자 값을 확인

```
inline unsigned int umax(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
정수 값

*_Y*<br/>
정수 값

### <a name="return-value"></a>반환 값

인수의 최대 숫자 값을 반환 합니다.

##  <a name="umin"></a>  umin

인수의 최소 숫자 값을 확인

```
inline unsigned int umin(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_X*<br/>
정수 값

*_Y*<br/>
정수 값

### <a name="return-value"></a>반환 값

인수의 최소 숫자 값을 반환 합니다.

## <a name="see-also"></a>참고자료

[Concurrency::direct3d 네임스페이스](concurrency-direct3d-namespace.md)
