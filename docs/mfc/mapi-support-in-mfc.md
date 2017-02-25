---
title: "MFC での MAPI サポート | Microsoft Docs"
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
  - "CDocument クラス, および MAPI"
  - "MAPI サポート (MFC で)"
  - "MAPI, MFC"
  - "MFC, MAPI サポート"
  - "OnFileSendMail メソッド"
  - "OnUpdateFileSendMail メソッド"
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# MFC での MAPI サポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス **CDocument**の Microsoft メッセージング アプリケーションのプログラム インターフェイス \(MAPI\) のサブセットに対する MFC のサポートを提供します。  具体的には、**CDocument** にメール サポートは、エンド ユーザーのコンピューター上にあり、その場合は標準コマンド ID を **ID\_FILE\_SEND\_MAIL**であるメール送信コマンドを有効にするかどうかを判断するメンバー関数があります。  このコマンドの MFC のハンドラー関数は、ユーザーが電子メールを介してドキュメントを送信できるようになります。  
  
> [!TIP]
>  MFC は全体の MAPI 関数のセットをカプセル化していても、MFC プログラムから Win32 API 関数を直接呼び出すことができます \(関数で直接呼び出すことができます。  
  
 アプリケーションでメール送信コマンドを使用することがよくあります。  MFC はドキュメント \(つまり、**CDocument**\-派生オブジェクト\) を添付ファイルとしてパッケージ化、メールとして送信する実装を提供します。  この添付ファイル \(シリアル化する\) ドキュメントの内容を保存するメール メッセージにファイル保存コマンドと等価です。  この実装は、ユーザーが電子メール アドレスを指定し、メール メッセージの件名とメッセージにテキストを追加する機会を提供するために、ユーザーのコンピューターの電子メール クライアントを要求します。  ユーザーはこれらの使い慣れたメール アプリケーションのユーザー インターフェイスを参照します。  この機能は **CDocument** の 2 種類のメンバー関数によって提供されます。: `OnFileSendMail` と `OnUpdateFileSendMail`。  
  
 MAPI が添付ファイルを送信するファイルを読み取る必要があります。  アプリケーションにデータ ファイルを `OnFileSendMail` 関数呼び出しで開いたまま、ファイルにアクセスする複数のプロセスとその共有モード開く必要があります。  
  
> [!NOTE]
>  クラス `COleDocument` の `OnFileSendMail` のオーバーライド バージョンが正しく複合ドキュメントを処理します。  
  
#### MFC の電子メール送信コマンドを実装するには  
  
1.  コマンド ID を **ID\_FILE\_SEND\_MAIL**にあるメニュー項目を追加するには、Visual C\+\+ は、メニュー エディターを使用します。  
  
     このコマンド ID は、AFXRES.H.のフレームワークに用意されます。  コマンドは、メニューに追加することはできますが、通常 **ファイル** メニューに追加されます。  
  
2.  手動でドキュメントのメッセージ マップに追加する:  
  
     [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/CPP/mapi-support-in-mfc_1.cpp)]  
  
    > [!NOTE]
    >  メッセージ マップのドキュメントが派生クラスにもかかわらず、このメッセージ マップでは **CDocument** または **COleDocument** からドキュメントの派生で機能します。正しい基本クラスのいずれにもなります。  
  
3.  アプリケーションをビルドします。  
  
 メールがサポートされている場合、MFC は、`OnUpdateFileSendMail` のメニュー項目が有効になり、それ以降の `OnFileSendMail`コマンドを処理します。  メール サポートが使用できない場合、MFC は自動的にメニュー項目を削除します。ユーザーが参照しません。  
  
> [!TIP]
>  前に説明したように、メッセージ マップ エントリを追加するのではなく、関数にメッセージをマップするクラスのプロパティ ウィンドウを使用します。  詳細については、「[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)」を参照してください。  
  
 関連情報については、[MAPI](../mfc/mapi.md) の概要を参照してください。  
  
 MAPI を有効にする **CDocument** のメンバー関数の詳細については、参照します:  
  
-   [CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)  
  
-   [CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)  
  
-   [COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)  
  
## 参照  
 [MAPI](../mfc/mapi.md)