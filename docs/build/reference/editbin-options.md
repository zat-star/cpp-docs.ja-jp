---
title: "EDITBIN オプション | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "editbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EDITBIN プログラム、オプション"
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# EDITBIN オプション
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

EDITBIN を使用すると、オブジェクト ファイル、実行可能ファイル、およびダイナミック リンク ライブラリ \(DLLs\) の内容を変更できます。  オプションは、EDITBIN で変更を指定します。  
  
 オプションを指定するには、オプション指定子の \- \(ダッシュ\) または \/ \(スラッシュ\) の後ろにオプション名を入力します。  オプション名の省略形は使用できません。  一部のオプションはコロンの後に指定された引数を受け取ります \(: \).  1 つのオプションの指定には、スペースやタブは挿入できません。  複数のオプションを指定する場合は、各オプションを 1 つ以上のスペースまたはタブで区切ります。  オプション名とキーワードの引数またはファイル名の引数では、大文字と小文字が区別されません。  たとえば、\-バインドと \/BIND は、同じことを意味します。  
  
 EDITBIN には、次のオプションがあります。  
  
|オプション|目的|  
|-----------|--------|  
|[\/ALLOWBIND](../../build/reference/allowbind.md)|DLL をバインドすることができるかどうかを指定します。|  
|[\/ALLOWISOLATION](../Topic/-ALLOWISOLATION.md)|DLL または実行可能ファイルのマニフェスト検索の動作を指定します。|  
|[\/APPCONTAINER](../../build/reference/appcontainer.md)|[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] のアプリケーションとかどうか AppContainer のアプリケーション内で実行するよう指定します。|  
|[\/BIND](../../build/reference/bind.md)|速度の読み込み時に指定したオブジェクトのエントリ ポイントのアドレスを設定します。|  
|[\/DYNAMICBASE](../../build/reference/dynamicbase.md)|DLL または実行可能イメージが ASLR \(ASLR\) を使用してロード時にランダムに再ベースかどうかを指定します。|  
|[\/ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Microsoft に内部エラーを報告します。|  
|[\/HEAP](../../build/reference/heap.md)|バイトの実行可能イメージのヒープのサイズを設定します。|  
|[\/HIGHENTROPYVA](../../build/reference/highentropyva.md)|DLL または実行可能イメージの高いエントロピ \(64 ビット\) の ASLR \(ASLR\) をサポートしているかどうかを指定します。|  
|[\/INTEGRITYCHECK](../Topic/-INTEGRITYCHECK.md)|読み込み時にデジタル署名をチェックするかどうかを指定します。|  
|[\/LARGEADDRESSAWARE](../Topic/-LARGEADDRESSAWARE.md)|かどうか 2 GB を超えるオブジェクトがアドレス指定します。|  
|[\/NOLOGO](../../build/reference/nologo-editbin.md)|EDITBIN の著作権情報を表示しません。|  
|[\/NXCOMPAT](../Topic/-NXCOMPAT.md)|実行可能イメージは Windows データ実行防止機能との互換性があるかどうかを指定します。|  
|[\/REBASE](../Topic/-REBASE.md)|指定されたオブジェクトのベース アドレスを設定します。|  
|[\/RELEASE](../../build/reference/release.md)|ヘッダーにチェックサムを設定します。|  
|[\/SECTION](../Topic/-SECTION%20\(EDITBIN\).md)|セクションの属性をオーバーライドします。|  
|[\/STACK](../../build/reference/stack.md)|バイトの実行可能イメージのスタックのサイズを設定します。|  
|[\/SUBSYSTEM](../../build/reference/subsystem.md)|実行する環境を指定します。|  
|[\/SWAPRUN](../../build/reference/swaprun.md)|実行可能イメージをスワップ ファイルにコピーする必要がある指定し、そこからことを実行します。|  
|[\/TSAWARE](../../build/reference/tsaware.md)|アプリケーションがマルチユーザー環境で動作するように設計されていることを示します。|  
|[\/VERSION](../../build/reference/version.md)|ヘッダーのバージョン番号を設定します。|  
  
## 参照  
 [C と C\+\+ のビルド ツール](../Topic/C-C++%20Build%20Tools.md)   
 [EDITBIN リファレンス](../Topic/EDITBIN%20Reference.md)