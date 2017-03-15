---
title: "インターネット クライアント アプリケーションの作成用の MFC クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], MFC"
  - "インターネット アプリケーション, MFC"
  - "インターネット クライアント アプリケーション, MFC"
  - "MFC, WinInet クラス"
  - "WinInet クラス, クラス"
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# インターネット クライアント アプリケーションの作成用の MFC クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC には、クライアント アプリケーションを作成するためのクラスとグローバル関数が用意されています。  インデントはクラスがその前の unindented クラスから派生されることを示します。  `CGopherFile` と `CHttpFile` は、たとえば `CInternetFile`から派生します。  これらのクラスとグローバル関数は AFX.H.で宣言された AFXINET.H で、`CFileFind`を除く宣言されています。  
  
## クラス  
  
-   [CInternetSession](../Topic/CInternetSession%20Class.md)  
  
-   [CInternetConnection](../Topic/CInternetConnection%20Class.md)  
  
    -   [CFtpConnection](../mfc/reference/cftpconnection-class.md)  
  
    -   [CGopherConnection](../mfc/reference/cgopherconnection-class.md)  
  
    -   [CHttpConnection](../mfc/reference/chttpconnection-class.md)  
  
-   [CInternetFile](../mfc/reference/cinternetfile-class.md)  
  
    -   [CGopherFile](../mfc/reference/cgopherfile-class.md)  
  
    -   [CHttpFile](../Topic/CHttpFile%20Class.md)  
  
-   [CFileFind](../mfc/reference/cfilefind-class.md)  
  
    -   [CFtpFileFind](../Topic/CFtpFileFind%20Class.md)  
  
    -   [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)  
  
-   [CGopherLocator](../Topic/CGopherLocator%20Class.md)  
  
-   [CInternetException](../mfc/reference/cinternetexception-class.md)  
  
## グローバル関数  
  
-   [AfxParseURL](../Topic/AfxParseURL.md)  
  
-   [AfxGetInternetHandleType](../Topic/AfxGetInternetHandleType.md)  
  
-   [AfxThrowInternetException](../Topic/AfxThrowInternetException.md)  
  
## 参照  
 [Win32 インターネット拡張機能 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの必要条件](../Topic/Prerequisites%20for%20Internet%20Client%20Classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)