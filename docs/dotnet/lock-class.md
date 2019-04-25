---
title: lock 클래스
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::lock::lock
- msclr::lock::is_locked
- msclr::lock.is_locked
- msclr::lock::acquire
- msclr::lock::try_acquire
- msclr::lock::release
- msclr::lock::operator==
- msclr::lock::operator!=
helpviewer_keywords:
- msclr::lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: 43418da36aa2d87608a9d672e4345d24011be0b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153442"
---
# <a name="lock-class"></a>lock 클래스

이 클래스는 여러 스레드에서 개체에 대 한 액세스를 동기화 하는 것에 대 한 잠금을 자동화 합니다.  생성 될 때 잠금을 획득 릴리스를 제거 하는 경우 및 잠금.

## <a name="syntax"></a>구문

```cpp
ref class lock;
```

## <a name="remarks"></a>설명

`lock` CLR 개체에 대해서만 사용할 수 있고 CLR 코드에만 사용할 수 있습니다.

잠금 클래스는 내부적으로 <xref:System.Threading.Monitor> 액세스를 동기화 합니다. 자세한 내용은 참조 된 문서를 참조 하세요.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|---------|-----------|
|[lock::lock](#lock)|생성을 `lock` 또는 전혀 사용 하지 않을 경우의 지정된 된 시간에 대 한 잠금을 영구적으로 획득 하려고 대기 하는 선택적 개체입니다.|
|[lock::~lock](#tilde-lock)|소멸을 `lock` 개체입니다.|

### <a name="public-methods"></a>public 메서드

|이름|설명|
|---------|-----------|
|[lock::acquire](#acquire)|지정 된 시간 또는 전혀 사용 하지 않을 경우의 잠금을 영구적으로 획득 하려고 대기 하는 필요에 따라 개체에 대 한 잠금을 획득 합니다.|
|[lock::is_locked](#is-locked)|잠금이 열리는지 여부를 나타냅니다.|
|[lock::release](#release)|잠금을 해제합니다.|
|[lock::try_acquire](#try-acquire)|지정된 된 시간 동안 대기 하 고 반환 개체에 대 한 잠금을 획득을 `bool` 예외를 throw 하는 대신 취득의 성공 여부를 보고 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|---------|-----------|
|[lock::operator&nbsp;bool](#operator-bool)|연산자를 사용 하 여 `lock` 조건식에서입니다.|
|[lock::operator==](#operator-equality)|같음 연산자입니다.|
|[lock::operator!=](#operator-inequality)|같지 않음 연산자입니다.|

## <a name="requirements"></a>요구 사항

**헤더 파일** \<msclr\lock.h >

**Namespace** msclr



## <a name="lock"></a>lock::lock

생성을 `lock` 또는 전혀 사용 하지 않을 경우의 지정된 된 시간에 대 한 잠금을 영구적으로 획득 하려고 대기 하는 선택적 개체입니다.

```cpp
template<class T> lock(
   T ^ _object
);
template<class T> lock(
   T ^ _object,
   int _timeout
);
template<class T> lock(
   T ^ _object,
   System::TimeSpan _timeout
);
template<class T> lock(
   T ^ _object,
   lock_later
);
```

### <a name="parameters"></a>매개 변수

*_object*<br/>
개체를 잠글 수입니다.

*_timeout*<br/>
시간 (밀리초) 또는 시간 제한 값을 <xref:System.TimeSpan>입니다.

### <a name="exceptions"></a>예외

Throw <xref:System.ApplicationException> 잠금 획득 시간 제한 전에 발생 하지 않습니다.

### <a name="remarks"></a>설명

생성자의 처음 세 개의 폼에서 잠금을 획득 하려고 `_object` 지정된 된 제한 시간 내에서 (또는 <xref:System.Threading.Timeout.Infinite> 지정 되지 않은 경우).

네 번째 형식의 생성자에서 잠금을 획득 하지 `_object`합니다. `lock_later` 구성원임을 확인 합니다 [lock_when 열거형](../dotnet/lock-when-enum.md)합니다. 사용 하 여 [lock::acquire](../dotnet/lock-acquire.md) 하거나 [lock::try_acquire](../dotnet/lock-try-acquire.md) 잠금을 획득 하기 위해이 경우.

소멸자가 호출 될 때에 자동으로 잠금이 해제 됩니다.

`_object` 일 수 없습니다 <xref:System.Threading.ReaderWriterLock>합니다.  이 경우 컴파일러 오류가 발생 합니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다. 클래스 자체에 잠금을 사용 하 여 내부 데이터에 대 한 액세스는 각 스레드에 대해 일치 하는지 확인 하십시오. 기본 응용 프로그램 스레드는 주기적으로 모든 작업자 스레드가 여전히 존재 하는지 확인 하려면 클래스의 동일한 인스턴스에서 잠금을 사용 합니다. 그러면 주 응용 프로그램 종료 모든 작업자 스레드가 해당 태스크를 완료 될 때까지 대기 합니다.

```cpp
// msl_lock_lock.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="tilde-lock"></a>lock::~lock

소멸을 `lock` 개체입니다.

```cpp
~lock();
```

### <a name="remarks"></a>설명

소멸자 호출 [lock::release](../dotnet/lock-release.md)합니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스 자체에 잠금을 사용 하 여 내부 데이터에 대 한 액세스는 각 스레드에 대해 일치 하는지 확인 하십시오.  기본 응용 프로그램 스레드는 주기적으로 모든 작업자 스레드가 여전히 존재 하는지 확인 하려면 클래스의 동일한 인스턴스에서 잠금을 사용 합니다. 그러면 주 응용 프로그램 종료 모든 작업자 스레드가 해당 태스크를 완료 될 때까지 대기 합니다.

```cpp
// msl_lock_dtor.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="acquire"></a>lock::acquire

지정 된 시간 또는 전혀 사용 하지 않을 경우의 잠금을 영구적으로 획득 하려고 대기 하는 필요에 따라 개체에 대 한 잠금을 획득 합니다.

```cpp
void acquire();
void acquire(
   int _timeout
);
void acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>매개 변수

*_timeout*<br/>
시간 (밀리초) 또는 시간 제한 값을 <xref:System.TimeSpan>입니다.

### <a name="exceptions"></a>예외

Throw <xref:System.ApplicationException> 잠금 획득 시간 제한 전에 발생 하지 않습니다.

### <a name="remarks"></a>설명

기본 제한 시간은 시간 제한 값을 제공 되지 않는 경우 <xref:System.Threading.Timeout.Infinite>합니다.

잠금을 이미 가져온 경우이 함수는 아무 작업도 수행 하지.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스 자체에 잠금을 사용 하 여 내부 데이터에 대 한 액세스는 각 스레드에 대해 일치 하는지 확인 하십시오. 기본 응용 프로그램 스레드는 주기적으로 모든 작업자 스레드가 여전히 존재 하는지 확인 하려면 클래스의 동일한 인스턴스에서 잠금을 사용 합니다. 그러면 주 응용 프로그램 종료 모든 작업자 스레드가 해당 태스크를 완료 될 때까지 대기 합니다.

```cpp
// msl_lock_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="is-locked"></a>lock::is_locked

잠금이 열리는지 여부를 나타냅니다.

```cpp
bool is_locked();
```

### <a name="return-value"></a>반환 값

`true` 잠금이 유지 되는 경우 `false` 그렇지 않은 경우.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스 자체에 잠금을 사용 하 여 내부 데이터에 대 한 액세스는 각 스레드에 대해 일치 하는지 확인 하십시오.  주 응용 프로그램 스레드는 주기적으로 확인 하는 경우 모든 작업자 스레드가 여전히 존재 하며 일까 지 모든 작업자 스레드가 끝나기를 대기 요소가 해당 작업을 완료 하는 클래스의 동일한 인스턴스에서 잠금을 사용 합니다.

```cpp
// msl_lock_is_locked.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l.is_locked()) { // check if we got the lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="operator-bool"></a>lock::operator bool

연산자를 사용 하 여 `lock` 조건식에서입니다.

```cpp
operator bool();
```

### <a name="return-value"></a>반환 값

`true` 잠금이 유지 되는 경우 `false` 그렇지 않은 경우.

### <a name="remarks"></a>설명

이 연산자를 실제로 변환 `_detail_class::_safe_bool` 는 보다 안전한 `bool` 정수 계열 형식으로 변환할 수 없기 때문입니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스 자체에 잠금을 사용 하 여 내부 데이터에 대 한 액세스는 각 스레드에 대해 일치 하는지 확인 하십시오. 기본 응용 프로그램 스레드는 주기적으로 모든 작업자 스레드가 여전히 존재 하는지 확인 하려면 클래스의 동일한 인스턴스에서 잠금을 사용 합니다. 주 응용 프로그램 종료 모든 작업자 스레드가 해당 태스크를 완료 될 때까지 대기 합니다.

```cpp
// msl_lock_op_bool.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l) { // use bool operator to check for lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="release"></a>lock::release

잠금을 해제합니다.

```cpp
void release();
```

### <a name="remarks"></a>설명

잠금이 열리는지 경우 `release` 아무 작업도 수행 합니다.

이 함수를 명시적으로 호출할 필요가 없습니다. 경우는 `lock` 개체 소멸자 호출 범위를 벗어나면 `release`합니다.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다. 클래스 자체에 잠금을 사용 하 여 내부 데이터에 대 한 액세스는 각 스레드에 대해 일치 하는지 확인 하십시오. 기본 응용 프로그램 스레드는 주기적으로 모든 작업자 스레드가 여전히 존재 하는지 확인 하려면 클래스의 동일한 인스턴스에서 잠금을 사용 합니다. 그러면 주 응용 프로그램 종료 모든 작업자 스레드가 해당 태스크를 완료 될 때까지 대기 합니다.

```cpp
// msl_lock_release.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="try-acquire"></a>lock::try_acquire

지정된 된 시간 동안 대기 하 고 반환 개체에 대 한 잠금을 획득을 `bool` 예외를 throw 하는 대신 취득의 성공 여부를 보고 합니다.

```cpp
bool try_acquire(
   int _timeout_ms
);
bool try_acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>매개 변수

*_timeout*<br/>
시간 (밀리초) 또는 시간 제한 값을 <xref:System.TimeSpan>입니다.

### <a name="return-value"></a>반환 값

`true` 잠금을 획득 하는 경우 `false` 그렇지 않은 경우.

### <a name="remarks"></a>설명

잠금을 이미 가져온 경우이 함수는 아무 작업도 수행 하지.

### <a name="example"></a>예제

이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다. 클래스 자체에 잠금을 사용 하 여 내부 데이터에 대 한 액세스는 각 스레드에 대해 일치 하는지 확인 하십시오. 기본 응용 프로그램 스레드는 주기적으로 모든 작업자 스레드가 여전히 존재 하는지 확인 하려면 클래스의 동일한 인스턴스에서 잠금을 사용 합니다. 그러면 주 응용 프로그램 종료 모든 작업자 스레드가 해당 태스크를 완료 될 때까지 대기 합니다.

```cpp
// msl_lock_try_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="operator-equality"></a>lock::operator==

같음 연산자입니다.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>매개 변수

*t*<br/>
같은지 비교할 개체입니다.

### <a name="return-value"></a>반환 값

반환 `true` 하는 경우 `t` 잠금의 개체와 같은지 `false` 그렇지 않은 경우.

### <a name="example"></a>예제

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="operator-inequality"></a>lock::operator!=

같지 않음 연산자입니다.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>매개 변수

*t*<br/>
같지 않은지 비교할 개체입니다.

### <a name="return-value"></a>반환 값

반환 `true` 하는 경우 `t` 잠금의 개체에서 다른 `false` 그렇지 않은 경우.

### <a name="example"></a>예제

```cpp
// msl_lock_op_ineq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   Object^ o2 = gcnew Object;
   lock l1(o1);
   if (l1 != o2) {
      Console::WriteLine("Inequal!");
   }
}
```

```Output
Inequal!
```