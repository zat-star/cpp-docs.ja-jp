---
title: "CFtpConnection クラス | Microsoft Docs"
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
  - "CFtpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFtpConnection クラス"
  - "FTP (ファイル転送プロトコル), 確立 (接続を)"
  - "インターネット接続, FTP"
  - "インターネット サービス, FTP"
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFtpConnection クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インターネット サーバーへの FTP 接続を管理し、そのサーバー上のフォルダーとファイルを直接処理することができます。  
  
## 構文  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFtpConnection::CFtpConnection](../Topic/CFtpConnection::CFtpConnection.md)|`CFtpConnection` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFtpConnection::Command](../Topic/CFtpConnection::Command.md)|FTP サーバーにコマンドを直接送信します。|  
|[CFtpConnection::CreateDirectory](../Topic/CFtpConnection::CreateDirectory.md)|サーバー ディレクトリを作成します。|  
|[CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md)|この接続の現在のディレクトリを取得します。|  
|[CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md)|URL として現在の接続の現在のディレクトリを取得します。|  
|[CFtpConnection::GetFile](../Topic/CFtpConnection::GetFile.md)|接続されたサーバーからファイルを取得します|  
|[CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md)|接続されたサーバー ファイルを開きます。|  
|[CFtpConnection::PutFile](../Topic/CFtpConnection::PutFile.md)|サーバーにファイルを設定します。|  
|[CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md)|サーバーからファイルを削除します。|  
|[CFtpConnection::RemoveDirectory](../Topic/CFtpConnection::RemoveDirectory.md)|サーバーから指定されたディレクトリを削除します。|  
|[CFtpConnection::Rename](../Topic/CFtpConnection::Rename.md)|サーバーのファイルの名前を変更します。|  
|[CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md)|現在の FTP ディレクトリを設定します。|  
  
## 解説  
 FTP は、MFC WinInet クラスによって認識される 3 人のインターネット サービスの 1 つです。  
  
 FTP のインターネット サーバーと通信するには、最初に [CInternetSession](../Topic/CInternetSession%20Class.md)のインスタンスを作成し、次に `CFtpConnection` のオブジェクトを作成します。  は `CFtpConnection` のオブジェクトを直接作成することはありません; なく、`CFtpConnection` のオブジェクトを作成し、オブジェクトへのポインターを返す呼び出し、[CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md)。  
  
 `CFtpConnection` と他の MFC インターネット クラスとの動作の詳細については、「[Win32 インターネット拡張機能 \(WinInet\)](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。  、HTTP、Gopher は、他の 2 種類のサポート サービスと通信する方法の詳細については、クラス [CHttpConnection](../../mfc/reference/chttpconnection-class.md) と [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)が表示されます。  
  
## 使用例  
 [CFtpFileFind](../Topic/CFtpFileFind%20Class.md) クラスの概要の例を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CInternetConnection](../Topic/CInternetConnection%20Class.md)  
  
 `CFtpConnection`  
  
## 必要条件  
 **ヘッダー:** afxinet.h  
  
## 参照  
 [CInternetConnection クラス](../Topic/CInternetConnection%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetConnection クラス](../Topic/CInternetConnection%20Class.md)   
 [CInternetSession クラス](../Topic/CInternetSession%20Class.md)