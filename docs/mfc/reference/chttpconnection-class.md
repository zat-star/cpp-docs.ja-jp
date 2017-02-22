---
title: "CHttpConnection クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHttpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHttpConnection クラス"
  - "接続 (サーバーに)"
  - "接続 (サーバーに), HTTP サーバー"
  - "接続 [C++], HTTP"
  - "HTTP 接続"
  - "HTTP サーバー, 接続"
  - "インターネット接続, HTTP"
  - "インターネット プロトコル"
  - "インターネット プロトコル, HTTP"
  - "インターネット サーバー, HTTP"
  - "プロトコル, HTTP"
  - "サーバー, 接続"
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHttpConnection クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

HTTP サーバーへの接続を管理します。  
  
## 構文  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHttpConnection::CHttpConnection](../Topic/CHttpConnection::CHttpConnection.md)|`CHttpConnection` オブジェクトを作成します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md)|HTTP 要求を開きます。|  
  
## 解説  
 HTTP は、MFC の WinInet クラスで実装されている 3 つのインターネット サービスの 1 つです。  
  
 `CHttpConnection` クラスには、コンストラクターと、1 つのメンバー関数 [OpenRequest](../Topic/CHttpConnection::OpenRequest.md) があります。このメンバー関数は、HTTP プロトコルによるサーバーへの接続を管理します。  
  
 HTTP サーバーと通信するには、最初に [CInternetSession](../Topic/CInternetSession%20Class.md) のインスタンスを作成し、次に [CHttpConnection](#_mfc_chttpconnection) オブジェクトを作成する必要があります。  `CHttpConnection` オブジェクトを直接作成することはできません。代わりに、[CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md) を呼び出して `CHttpConnection` オブジェクトを作成して、そのポインターを返します。  
  
 MFC インターネット クラスにおける `CHttpConnection` の使い方の詳細については、「[Win32 インターネット拡張機能 \(WinInet\)](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。  サポートされているほかの 2 つのプロトコル gopher と FTP を使ってサーバーに接続する方法の詳細については、「[CGopherConnection](../../mfc/reference/cgopherconnection-class.md)」クラスと「[CFtpConnection](../../mfc/reference/cftpconnection-class.md)」クラスを参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CInternetConnection](../Topic/CInternetConnection%20Class.md)  
  
 `CHttpConnection`  
  
## 必要条件  
 **ヘッダー:** afxinet.h  
  
## 参照  
 [CInternetConnection クラス](../Topic/CInternetConnection%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetConnection クラス](../Topic/CInternetConnection%20Class.md)   
 [CHttpFile クラス](../Topic/CHttpFile%20Class.md)