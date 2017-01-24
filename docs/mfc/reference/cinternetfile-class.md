---
title: "CInternetFile クラス | Microsoft Docs"
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
  - "CInternetFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetFile クラス"
  - "インターネット ファイル"
  - "インターネット ファイル, CInternetFile クラス"
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInternetFile クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インターネット プロトコルを使用するリモート システム上のファイルへのアクセスを提供します。  
  
## 構文  
  
```  
  
class CInternetFile : public CStdioFile  
  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CInternetFile::CInternetFile](../Topic/CInternetFile::CInternetFile.md)|`CInternetFile` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CInternetFile::Abort](../Topic/CInternetFile::Abort.md)|ファイルを閉しました、すべての警告とエラーを無視されます。|  
|[CInternetFile::Close](../Topic/CInternetFile::Close.md)|`CInternetFile` を閉じ、リソースを解放します。|  
|[CInternetFile::Flush](../Topic/CInternetFile::Flush.md)|書き込みバッファーの内容をフラッシュし、メモリ データをターゲット コンピューターに書き込むようになります。|  
|[CInternetFile::GetLength](../Topic/CInternetFile::GetLength.md)|ファイルのサイズを返します。|  
|[CInternetFile::Read](../Topic/CInternetFile::Read.md)|指定したバイト数を読み取ります。|  
|[CInternetFile::ReadString](../Topic/CInternetFile::ReadString.md)|文字ストリームを読み取ります。|  
|[CInternetFile::Seek](../Topic/CInternetFile::Seek.md)|開いているファイル ポインターを移動します。|  
|[CInternetFile::SetReadBufferSize](../Topic/CInternetFile::SetReadBufferSize.md)|データを読み込むバッファーのサイズを設定します。|  
|[CInternetFile::SetWriteBufferSize](../Topic/CInternetFile::SetWriteBufferSize.md)|データを書き込むバッファーのサイズを設定します。|  
|[CInternetFile::Write](../Topic/CInternetFile::Write.md)|指定されたバイト数を書き込みます。|  
|[CInternetFile::WriteString](../Topic/CInternetFile::WriteString.md)|ファイルに null で終わる文字列を書き込みます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CInternetFile::operator HINTERNET](../Topic/CInternetFile::operator%20HINTERNET.md)|インターネット ハンドルのキャスト演算子。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CInternetFile::m\_hFile](../Topic/CInternetFile::m_hFile.md)|ファイルのハンドル。|  
  
## 解説  
 [CHttpFile](../Topic/CHttpFile%20Class.md) ファイル クラスと [CGopherFile](../../mfc/reference/cgopherfile-class.md) ファイル クラスの基本クラスを提供します。  `CInternetFile` オブジェクトを直接構築することはできません。  代わりに、[CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md) または [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md) を呼び出して、派生クラスのオブジェクトを作成します。  [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md) を呼び出して、`CInternetFile` オブジェクトを作成することもできます。  
  
 `CInternetFile` では、`CInternetFile` のメンバー関数 **Open**、`LockRange`、`UnlockRange`、および `Duplicate` は、実装されていません。  `CInternetFile` オブジェクトでこれらの関数を呼び出すと、[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md) になります。  
  
 MFC インターネット クラスにおける `CInternetFile` の使い方の詳細については、「[Win32 インターネット拡張機能 \(WinInet\)](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../Topic/CStdioFile%20Class.md)  
  
 `CInternetFile`  
  
## 必要条件  
 **ヘッダー:** afxinet.h  
  
## 参照  
 [CStdioFile クラス](../Topic/CStdioFile%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetConnection クラス](../Topic/CInternetConnection%20Class.md)