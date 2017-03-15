---
title: "AUTOCLIK と AUTODRIV を使用したリモート オートメーションの実行 | Microsoft Docs"
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
  - "AUTOCLIK サンプル [MFC]"
ms.assetid: 8900c0de-8dba-4f0a-8d9e-7db77a1f4f46
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# AUTOCLIK と AUTODRIV を使用したリモート オートメーションの実行
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

AUTOCLIK では、リモート オートメーションの詳細については、基本クラスとして使用できる単純なオートメーション サーバー サンプル アプリケーションです。  また、オートメーション クライアントの単純なアプリケーションでドライブ AUTOCLIK です。  リモート オートメーションを示すために使用できます。  
  
#### AUTOCLIK.EXE を 2 台のコンピューターにインストールし、リモート オートメーションを使用して実行できます。  
  
1.  開発用コンピューターに [AUTOCLIK](../top/visual-cpp-samples.md) サンプル アプリケーションをインストールします。  
  
2.  AUTOCLIK.EXE をビルドします。  
  
3.  スタンドアロン スキーム AUTOCLIK.EXE を実行し、次にする。  これは、オートメーション サーバーとして登録します。  
  
4.  AUTOCLIK.EXE をリモート コンピューターにコピーして、そこに実行し、よりします。  
  
5.  ローカル コンピューターの AUTODRIV.EXE を実行し、実行することが AUTOCLIK.EXE が開始されることを確認します。  AUTODRIV.EXE の詳細を確認するには、[AUTOCLIK](../top/visual-cpp-samples.md)を参照してください。  
  
6.  リモート コンピューターで、AUTMGR32.EXE \(オートメーション マネージャー\) を起動します。  
  
7.  リモート コンピューターで、RACMGR32.EXE \(リモート オートメーション接続マネージャー\) を起動します。  
  
8.  リモート オートメーション接続マネージャーで、**OLE クラス** の一覧から AutoClik.Document を選択します。  
  
9. AutoClik.Document へのクライアント アクセスを許可するように **クライアント アクセス** タブからシステム セキュリティ ポリシーをクリックします。  
  
10. ローカル コンピューターで、RACMGR32.EXE を起動し、**OLE クラス** の一覧から AutoClik.Document を選択します。  
  
11. **サーバー接続** タブから、リモート コンピューターのネットワーク アドレスと適切なネットワーク プロトコルを選択します。  
  
12. まだ **OLE クラス** のリスト ボックスで選択 AutoClik.Document が `Register` メニューから **リモート** コマンドを選択します。  
  
13. ローカル コンピューター、実行された AUTODRIV.EXE または等価 AUTOCLIK.MAK Visual Basic の Visual Basic プロジェクトがある場合は、MFC ではなく、クライアント。  
  
 リモート コンピューターで、ローカル クライアントから開始コマンドを実行している AUTOCLIK を参照できるようになります。  
  
## 参照  
 [リモート オートメーション](../mfc/remote-automation.md)