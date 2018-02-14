---
title: "AUTOCLIK と AUTODRIV を使用してリモート オートメーションの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: AUTOCLIK sample [MFC]
ms.assetid: 8900c0de-8dba-4f0a-8d9e-7db77a1f4f46
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 791655047eaf07732e1e006e8cc3ea8e7dec4727
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="running-remote-automation-using-autoclik-and-autodriv"></a>AUTOCLIK と AUTODRIV を使用したリモート オートメーションの実行
AUTOCLIK は、元の詳細については、リモート オートメーションのベースとして使用できる単純なオートメーション サーバー サンプル アプリケーションです。 AUTODRIV は AUTOCLIK を推進する単純なオートメーション クライアント アプリケーションです。 リモート オートメーションをデモンストレーションするのにには、それらを使用できます。  
  
#### <a name="to-install-autoclikexe-on-two-machines-and-drive-it-using-remote-automation"></a>AUTOCLIK をインストールするには2 上の exe ファイルがコンピューターし、リモート オートメーションを使用してドライブ  
  
1.  インストール、 [AUTOCLIK](../visual-cpp-samples.md)サンプル アプリケーションを開発コンピューターにします。  
  
2.  AUTOCLIK をビルドします。EXE です。  
  
3.  AUTOCLIK を実行します。スタンドアロンの EXE の方式し、シャット ダウンします。 オートメーション サーバーとしてこれ登録されます。  
  
4.  AUTOCLIK をコピーします。リモート コンピューターに EXE は、実行し、シャット ダウンします。  
  
5.  AUTODRIV を実行します。ローカル上の exe ファイル コンピューターを実行することによって AUTOCLIK が開始されることを確認してください。EXE です。 AUTODRIV に関する詳細を確認します。実行可能ファイルを参照してください[AUTOCLIK](../visual-cpp-samples.md)です。  
  
6.  リモートのコンピューターでは、AUTMGR32 を起動します。EXE (オートメーション マネージャー)。  
  
7.  リモートのコンピューターでは、RACMGR32 を起動します。EXE (リモート オートメーション接続マネージャー)。  
  
8.  リモート オートメーション接続マネージャーで、選択から AutoClik.Document、 **OLE クラス** ボックスの一覧です。  
  
9. システム セキュリティ ポリシーの選択、**クライアント アクセス**AutoClik.Document にクライアント アクセスを許可する タブ。  
  
10. ローカルのコンピューターでは、RACMGR32 を起動します。EXE およびから select AutoClik.Document、 **OLE クラス** ボックスの一覧です。  
  
11. **サーバー接続** タブで、リモート コンピューターと適切なネットワーク プロトコルのネットワーク アドレスを選択します。  
  
12. AutoClik.Document 静止で選択されていると、 **OLE クラス**ボックスの一覧で、選択、**リモート**コマンドを`Register`メニュー。  
  
13. ローカル コンピューターの AUTODRIV を実行します。EXE または同等の AUTOCLIK です。MAK Visual Basic プロジェクトの場合は、MFC ではなく、Visual Basic にするクライアント。  
  
 リモートのコンピューターでようになりましたことができますをローカル クライアントから開始されたコマンドを実行する AUTOCLIK を参照してください。  
  
## <a name="see-also"></a>参照  
 [リモート オートメーション](../mfc/remote-automation.md)

