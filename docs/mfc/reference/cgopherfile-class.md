---
title: "CGopherFile クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGopherFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherFile クラス"
  - "gopher プロトコル ファイル"
  - "インターネット, Gopher"
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CGopherFile クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

gopher サーバー上のファイルを検索し、読み込む機能が用意されています。  
  
> [!NOTE]
>  Windows XP プラットフォームで動作しませんが、以前のプラットフォーム上で動作し続けるため、クラス `CGopherConnection`、`CGopherFile`、`CGopherFileFind`、`CGopherLocator` およびメンバーの使用は推奨されていません。  
  
## 構文  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CGopherFile::CGopherFile](../Topic/CGopherFile::CGopherFile.md)|`CGopherFile` オブジェクトを構築します。|  
  
## 解説  
 gopher サービスは、ユーザーが情報を検索するためのメニュー システムのインターフェイスとして Gopher の各ファイルにデータ サービスをため、この機能は主に書き込むことはできません。  `CGopherFile` のメンバー関数 **\[書き込み\]**、`WriteString`と `Flush` は `CGopherFile`用に実装されていません。  `CGopherFile` これらの関数を呼び出して、は、オブジェクト [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)します。  
  
 `CGopherFile` と他の MFC インターネット クラスとの動作の詳細については、「[Win32 インターネット拡張機能 \(WinInet\)](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../Topic/CStdioFile%20Class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## 必要条件  
 **ヘッダー:** afxinet.h  
  
## 参照  
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator クラス](../Topic/CGopherLocator%20Class.md)   
 [CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection クラス](../../mfc/reference/cgopherconnection-class.md)