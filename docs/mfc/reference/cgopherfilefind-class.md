---
title: "CGopherFileFind クラス | Microsoft Docs"
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
  - "CGopherFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherFileFind クラス"
  - "ファイルの検索 [C++]"
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherFileFind クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

gopher サーバーのインターネット ファイル検索を支援します。  
  
> [!NOTE]
>  Windows XP プラットフォームで動作しませんが、以前のプラットフォーム上で動作し続けるため、クラス `CGopherConnection`、`CGopherFile`、`CGopherFileFind`、`CGopherLocator` およびメンバーの使用は推奨されていません。  
  
## 構文  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CGopherFileFind::CGopherFileFind](../Topic/CGopherFileFind::CGopherFileFind.md)|`CGopherFileFind` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md)|gopher サーバーのファイルを検索します。|  
|[CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md)|前の呼び出しの [FindFile](../Topic/CGopherFileFind::FindFile.md)にファイル検索を続けます。|  
|[CGopherFileFind::GetCreationTime](../Topic/CGopherFileFind::GetCreationTime.md)|指定したファイルが作成された時刻を取得します。|  
|[CGopherFileFind::GetLastAccessTime](../Topic/CGopherFileFind::GetLastAccessTime.md)|指定したファイルが最終アクセス時刻を取得します。|  
|[CGopherFileFind::GetLastWriteTime](../Topic/CGopherFileFind::GetLastWriteTime.md)|指定したファイルが最後に記述された時間を取得します。|  
|[CGopherFileFind::GetLength](../Topic/CGopherFileFind::GetLength.md)|バイト見つかったファイルの長さを取得します。|  
|[CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md)|`CGopherLocator` のオブジェクトを取得します。|  
|[CGopherFileFind::GetScreenName](../Topic/CGopherFileFind::GetScreenName.md)|Gopher の各画面の名前を取得します。|  
|[CGopherFileFind::IsDots](../Topic/CGopherFileFind::IsDots.md)|ファイルを反復処理している間、現在のディレクトリと親ディレクトリのマーカーのテスト。|  
  
## 解説  
 `CGopherFileFind` は検索を開始し、ファイルを探し、ファイルの URL を返すメンバー関数があります。  
  
 インターネット検索とローカル ファイル用にデザインされたそのほかの MFC クラスは [CFtpFileFind](../Topic/CFtpFileFind%20Class.md) と [CFileFind](../../mfc/reference/cfilefind-class.md)が含まれます。  `CGopherFileFind`とともに、これらのクラスは、ユーザーがサーバーのプロトコル、ファイルの種類、または場所 \(ローカル コンピューターまたはリモート サーバー上\) に関係なく、特定のファイルを検索できるようにシームレスな機構を提供します。HTTP で検索に必要なファイルの直接処理をサポートしないため、HTTP サーバーの検索の MFC クラスがないことに注意してください。  
  
> [!NOTE]
>  `CGopherFileFind` は、基本クラス [CFileFind](../../mfc/reference/cfilefind-class.md)の次のメンバー関数をサポートしていません:  
  
-   [GetRoot](../Topic/CFileFind::GetRoot.md)  
  
-   [GetFileName](../Topic/CFileFind::GetFileName.md)  
  
-   [GetFilePath](../Topic/CFileFind::GetFilePath.md)  
  
-   [GetFileTitle](../Topic/CFileFind::GetFileTitle.md)  
  
-   [GetFileURL](../Topic/CFileFind::GetFileURL.md)  
  
 また、`CGopherFileFind`を使用すると、`CFileFind` のメンバー関数 [IsDots](../Topic/CFileFind::IsDots.md)**FALSE**は常にです。  
  
 `CGopherFileFind` およびそのほかの WinInet クラスを使用する方法の詳細については、" " [WinInet するインターネットのプログラミング](../../mfc/win32-internet-extensions-wininet.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## 必要条件  
 **ヘッダー:** afxinet.h  
  
## 参照  
 [CFileFind クラス](../../mfc/reference/cfilefind-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind クラス](../Topic/CFtpFileFind%20Class.md)   
 [CFileFind クラス](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile クラス](../Topic/CHttpFile%20Class.md)