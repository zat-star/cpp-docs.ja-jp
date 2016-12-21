---
title: "CFileFind クラス | Microsoft Docs"
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
  - "CFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileFind クラス"
  - "ファイル [C++], 検索"
  - "インターネット ファイル [C++], 検索"
  - "ローカル ファイル"
  - "ローカル ファイル, 検索"
  - "URL [C++], 検索"
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileFind クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インターネット ファイル検索を実行するローカル ファイル検索を実行し、[CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) と [CFtpFileFind](../Topic/CFtpFileFind%20Class.md)の基本クラスです。  
  
## 構文  
  
```  
class CFileFind : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFileFind::CFileFind](../Topic/CFileFind::CFileFind.md)|`CFileFind` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFileFind::Close](../Topic/CFileFind::Close.md)|検索の要求を終了します。|  
|[CFileFind::FindFile](../Topic/CFileFind::FindFile.md)|指定されたファイル名が検索されます。|  
|[CFileFind::FindNextFile](../Topic/CFileFind::FindNextFile.md)|前の呼び出しの [FindFile](../Topic/CFileFind::FindFile.md)にファイル検索を続けます。|  
|[CFileFind::GetCreationTime](../Topic/CFileFind::GetCreationTime.md)|ファイルが作成された時刻を取得します。|  
|[CFileFind::GetFileName](../Topic/CFileFind::GetFileName.md)|名前を、見つかったファイルの拡張子、取得します|  
|[CFileFind::GetFilePath](../Topic/CFileFind::GetFilePath.md)|見つかったファイルの完全なパスを取得します。|  
|[CFileFind::GetFileTitle](../Topic/CFileFind::GetFileTitle.md)|見つかったファイルのタイトルを取得します。  タイトルは拡張子は含まれません。|  
|[CFileFind::GetFileURL](../Topic/CFileFind::GetFileURL.md)|URL を、見つかったファイルのファイル パスを含む\) を取得します。|  
|[CFileFind::GetLastAccessTime](../Topic/CFileFind::GetLastAccessTime.md)|ファイルが最後にアクセスされていた時間を取得します。|  
|[CFileFind::GetLastWriteTime](../Topic/CFileFind::GetLastWriteTime.md)|ファイルが最後に変更され、保存された時間を取得します。|  
|[CFileFind::GetLength](../Topic/CFileFind::GetLength.md)|バイト見つかったファイルの長さを取得します。|  
|[CFileFind::GetRoot](../Topic/CFileFind::GetRoot.md)|見つかったファイルのルート ディレクトリを取得します。|  
|[CFileFind::IsArchived](../Topic/CFileFind::IsArchived.md)|見つかったファイルがアーカイブされているかどうかを判定します。|  
|[CFileFind::IsCompressed](../Topic/CFileFind::IsCompressed.md)|見つかったファイルを圧縮するかどうかを判定します。|  
|[CFileFind::IsDirectory](../Topic/CFileFind::IsDirectory.md)|見つかったファイルがディレクトリにあるかどうかを判定します。|  
|[CFileFind::IsDots](../Topic/CFileFind::IsDots.md)|見つかったファイルの名前に名前が「」にあるかどうかを判定します または「。」、実際にあるディレクトリに示します。|  
|[CFileFind::IsHidden](../Topic/CFileFind::IsHidden.md)|見つかったファイルが隠しファイルかどうかを判定します。|  
|[CFileFind::IsNormal](../Topic/CFileFind::IsNormal.md)|見つかったファイルが正常であるかどうかを判定します \(つまり、他の属性はありません\)。|  
|[CFileFind::IsReadOnly](../Topic/CFileFind::IsReadOnly.md)|見つかったファイルが読み取り専用かどうかを判断します。|  
|[CFileFind::IsSystem](../Topic/CFileFind::IsSystem.md)|見つかったファイルがシステム ファイルかどうかを判定します。|  
|[CFileFind::IsTemporary](../Topic/CFileFind::IsTemporary.md)|見つかったファイルが一時的であるかどうかを判定します。|  
|[CFileFind::MatchesMask](../Topic/CFileFind::MatchesMask.md)|検索するファイルのファイル属性を示します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFileFind::CloseContext](../Topic/CFileFind::CloseContext.md)|現在のの検索ハンドルで指定されたファイルを閉じます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CFileFind::m\_pTM](../Topic/CFileFind::m_pTM.md)|`CAtlTransactionManager` オブジェクトへのポインター。|  
  
## 解説  
 `CFileFind` は検索を開始し、ファイルを探し、ファイルの名前、タイトル、またはパスを返すメンバー関数があります。  インターネットの検索に、メンバー関数 [GetFileURL](../Topic/CFileFind::GetFileURL.md) は、ファイルの URL を返します。  
  
 `CFileFind` は、特定のサーバー型を検索するように設計された 2 つが他の MFC クラスの基本クラスです: `CGopherFileFind` は、FTP サーバーを gopher サーバーと `CFtpFileFind` の使用は特にともに使用します。  また、この 3 種類のクラスは、クライアントが、ローカル コンピューターまたはリモート サーバーのサーバーのプロトコル、ファイルの種類、または場所に関係なく、ファイルを検出できるようにシームレスな機構を提供します。  
  
 次のコードは、各ファイルの名前を印刷する現在のディレクトリのすべてのファイルを列挙します:  
  
 [!code-cpp[NVC_MFCFiles#31](../../mfc/codesnippet/CPP/cfilefind-class_1.cpp)]  
  
 例を避けるために、このコードは C\+\+ ライブラリの `cout` の標準クラスを使用します。  グラフィカル ユーザー インターフェイスを持つ `cout` の行はプログラムで `CListBox::AddString`の呼び出し、たとえば、置き換えることができます。  
  
 `CFileFind` およびそのほかの WinInet クラスを使用する方法の詳細については、" " [WinInet するインターネットのプログラミング](../../mfc/win32-internet-extensions-wininet.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CFileFind`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind クラス](../Topic/CFtpFileFind%20Class.md)   
 [CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile クラス](../Topic/CHttpFile%20Class.md)