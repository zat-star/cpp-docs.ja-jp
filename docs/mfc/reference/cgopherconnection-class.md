---
title: "CGopherConnection クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGopherConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherConnection クラス"
  - "接続 (サーバーに)"
  - "接続 (サーバーに), gopher サーバー"
  - "gopher プロトコル"
  - "gopher サーバー"
  - "インターネット接続, Gopher"
  - "インターネット サーバー, Gopher"
  - "プロトコル, Gopher"
  - "サーバー, 接続"
  - "サービス, Gopher"
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherConnection クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

gopher インターネット サーバーへの接続を管理します。  
  
> [!NOTE]
>  Windows XP プラットフォームで動作しませんが、以前のプラットフォーム上で動作し続けるため、クラス `CGopherConnection`、`CGopherFile`、`CGopherFileFind`、`CGopherLocator` およびメンバーの使用は推奨されていません。  
  
## 構文  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CGopherConnection::CGopherConnection](../Topic/CGopherConnection::CGopherConnection.md)|`CGopherConnection` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md)|[CGopherLocator](../Topic/CGopherLocator%20Class.md) のオブジェクトを gopher サーバーのファイルを見つけるために作成します。|  
|[CGopherConnection::GetAttribute](../Topic/CGopherConnection::GetAttribute.md)|Gopher の各オブジェクトに関する情報を取得する属性。|  
|[CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md)|gopher ファイルを開きます。|  
  
## 解説  
 gopher サービスは、MFC WinInet クラスによって認識されるインターネット サービスの 1 "です。  
  
 クラス `CGopherConnection` は、Gopher の各サービスを管理する 3 種類のメンバー関数、およびコンストラクターが含まれています: [OpenFile](../Topic/CGopherConnection::OpenFile.md)、[CreateLocator](../Topic/CGopherConnection::CreateLocator.md)と [GetAttribute](../Topic/CGopherConnection::GetAttribute.md)。  
  
 gopher インターネット サーバーと通信するには、最初に `CGopherConnection` のオブジェクトを作成し、オブジェクトへのポインターを返す [CInternetSession](../Topic/CInternetSession%20Class.md)のインスタンスを作成し、次に [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md)を呼び出します。  `CGopherConnection` オブジェクトを直接構築することはできません。  
  
 `CGopherConnection` と他の MFC インターネット クラスとの動作の詳細については、「[Win32 インターネット拡張機能 \(WinInet\)](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。  他の 2 種類の使用方法の詳細については、サポートされているインターネット サービス、FTP、HTTP [CHttpConnection](../../mfc/reference/chttpconnection-class.md) は、クラスと [CFtpConnection](../../mfc/reference/cftpconnection-class.md)が表示されます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CInternetConnection](../Topic/CInternetConnection%20Class.md)  
  
 `CGopherConnection`  
  
## 必要条件  
 **ヘッダー:** afxinet.h  
  
## 参照  
 [CInternetConnection クラス](../Topic/CInternetConnection%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFtpConnection クラス](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection クラス](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection クラス](../Topic/CInternetConnection%20Class.md)   
 [CGopherLocator クラス](../Topic/CGopherLocator%20Class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession クラス](../Topic/CInternetSession%20Class.md)