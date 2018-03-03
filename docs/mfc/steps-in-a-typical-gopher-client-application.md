---
title: "典型的な Gopher クライアント アプリケーションでの手順 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5108e997336e53434ad33030c0e79be027aa4a98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-gopher-client-application"></a>典型的な Gopher クライアント アプリケーションの作成手順
次の表は、典型的な gopher クライアント アプリケーションで必要な手順を示します。  
  
|目標|操作を実行します。|効果|  
|---------------|----------------------|-------------|  
|Gopher セッションを開始します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|WinInet を初期化し、サーバーに接続します。|  
|Gopher サーバーに接続します。|使用して[代わり](../mfc/reference/cinternetsession-class.md#getgopherconnection)です。|返します、[関数](../mfc/reference/cgopherconnection-class.md)オブジェクト。|  
|Gopher 内の最初のリソースを検索します。|使用して[CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile)です。|最初のファイルを検索します。 ファイルが見つからない場合は、FALSE を返します。|  
|Gopher で次のリソースを検索します。|使用して[CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile)です。|次のファイルを検索します。 ファイルが見つからない場合は、FALSE を返します。|  
|によって検出されたファイルを開く**FindFile**または`FindNextFile`の読み取りにします。|使用して gopher ロケーターを取得[なった](../mfc/reference/cgopherfilefind-class.md#getlocator)です。 使用して[CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)です。|ロケーターに指定されたファイルを開きます。 `OpenFile`返します、 [CGopherFile](../mfc/reference/cgopherfile-class.md)オブジェクト。|  
|指定した gopher ロケーターを使用してファイルを開きます。|使用して、gopher ロケーターを作成[CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator)です。 使用して[CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)です。|ロケーターに指定されたファイルを開きます。 `OpenFile`返します、 [CGopherFile](../mfc/reference/cgopherfile-class.md)オブジェクト。|  
|ファイルから読み取られました。|使用して[CGopherFile](../mfc/reference/cgopherfile-class.md)です。|指定した入力バッファーを使用して、バイト数を読み取ります。|  
|例外を処理する|使用して、 [CInternetException](../mfc/reference/cinternetexception-class.md)クラスです。|すべての一般的なインターネット例外タイプを処理します。|  
|Gopher セッションを終了します。|破棄、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|開いているファイル ハンドルと接続を自動的にクリーンアップします。|  
  
## <a name="see-also"></a>参照  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
