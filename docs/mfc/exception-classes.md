---
title: 예외 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.exception
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
ms.openlocfilehash: 99a2764dcad15267b1aab8a60951f99f21352726
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392871"
---
# <a name="exception-classes"></a>예외 클래스

클래스 라이브러리는 `CException` 클래스를 기반으로 예외 처리 메커니즘을 제공합니다. 응용 프로그램 프레임 워크는 해당 코드에서 예외를 사용합니다. 사용자도 자신의 코드에서 예외를 사용할 수 있습니다. 자세한 내용은 문서 참조 [예외](../mfc/exception-handling-in-mfc.md)합니다. 사용자는 `CException`에서 고유한 예외 형식을 파생할 수 있습니다.

MFC는 지원하는 모든 예외에 대한 예외 클래스뿐만 아니라 사용자가 고유한 예외를 파생할 수 있는 예외 클래스를 제공합니다.

[CException](../mfc/reference/cexception-class.md)<br/>
예외에 대한 기본 클래스입니다.

[CArchiveException](../mfc/reference/carchiveexception-class.md)<br/>
아카이브 예외입니다.

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
DAO 데이터베이스 작업의 오류로 인해 발생하는 예외입니다.

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
ODBC 데이터베이스 처리 중 오류로 인해 발생하는 예외입니다.

[CFileException](../mfc/reference/cfileexception-class.md)<br/>
파일 관련 예외입니다.

[CMemoryException](../mfc/reference/cmemoryexception-class.md)<br/>
메모리 부족 예외입니다.

[CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)<br/>
지원되지 않은 기능을 사용함으로써 발생하는 예외입니다.

[COleException](../mfc/reference/coleexception-class.md)<br/>
OLE 처리 중 오류로 인해 발생하는 예외입니다. 이 클래스는 컨테이너 및 서버에서 모두 사용됩니다.

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
자동화 중 오류로 인해 발생하는 예외입니다. 자동화 예외는 자동화 서버에 의해 throw되고 자동화 클라이언트에 의해 catch됩니다.

[CResourceException](../mfc/reference/cresourceexception-class.md)<br/>
Windows 리소스 로드 오류로 인해 발생하는 예외입니다.

[CUserException](../mfc/reference/cuserexception-class.md)<br/>
사용자가 시작한 작업을 중지하는 데 사용된 예외입니다. 일반적으로, 이 예외가 throw되기 전에 사용자에게 문제에 대한 알림이 제공됩니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
