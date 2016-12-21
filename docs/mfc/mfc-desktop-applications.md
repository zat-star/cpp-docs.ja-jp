---
title: "MFC デスクトップ アプリケーション | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MFC"
  - "mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス ライブラリ, MFC"
  - "ライブラリ, MFC"
  - "MFC, 概要 (MFC の)"
ms.assetid: 7101cb18-a681-495c-8f2b-069ad20c72f7
caps.latest.revision: 26
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC デスクトップ アプリケーション
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation Class \(MFC\) ライブラリは、Win32 お呼びCOM API の多くにオブジェクト指向のラッパーを提供します。  かなりシンプルなデスクトップ アプリケーションの作成にも使用できますが、複数のコントロールを使用する複雑なユーザー インターフェイスを開発する必要がある場合に最も役立ちます。  MFC を使用すると、Office スタイルのユーザー インターフェイスを持つアプリケーションを作成できます。  
  
 『MFC リファレンス』では、Microsoft Foundation Class ライブラリ を構成するクラス、グローバル関数、グローバル変数、マクロについて説明しています。  
  
 各クラスの説明に含まれる階層図の一部は、基底クラスの位置を知るのに便利です。  『MFC リファレンス』では、継承されたメンバー関数、継承された演算子の説明はしていません。  これらの関数については、階層図の基底クラスの説明を参照してください。  
  
 各クラスのトピックは、クラス概要、カテゴリ別のメンバー要約、メンバー関数、オーバーロードされた演算子、およびデータ メンバーについて説明しています。  
  
 パブリック クラス メンバーおよびプロテクト クラス メンバーは、アプリケーション プログラムや派生クラスでよく使われるものだけを取り上げています。  全クラス メンバーの一覧は、クラスのヘッダー ファイルを参照してください。  
  
> [!IMPORTANT]
>  MFC クラスとそのメンバーは、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
>   
>  マルチバイト文字エンコード \(MBCS\) の MFC ライブラリ \(DLL\) は、Visual Studio に含まれなくなりましたが、Visual Studio アドオンとして使用できます。  詳細については、「[MFC MBCS DLL アドオン](../mfc/mfc-mbcs-dll-add-on.md)」を参照してください。  
  
## このセクションの内容  
 [概念](../mfc/mfc-concepts.md)  
 MFC のトピックの概念に関する記事です。  
  
 [階層図](../mfc/hierarchy-chart.md)  
 クラス ライブラリのクラスの関係がわかりやすく図で示されています。  
  
 [クラスの概要](../mfc/class-library-overview.md)  
 MFC ライブラリのクラスをカテゴリ別に一覧表示します。  
  
 [チュートリアル](../mfc/walkthroughs-mfc.md)  
 MFC ライブラリ機能に関連するさまざまなタスクを解説している記事を紹介します。  
  
 [テクニカル ノート](../mfc/mfc-technical-notes.md)  
 MFC 開発チームの執筆によるクラス ライブラリに関する技術情報へのリンクを提供します。  
  
 [MFC のカスタマイズ](../mfc/customization-for-mfc.md)  
 MFC アプリケーションをカスタマイズするためのヒントを示します。  
  
 [クラス](../Topic/MFC%20Classes.md)  
 MFC クラスへのリンクおよび MFC クラスのヘッダー ファイル情報が用意されています。  
  
 [内部クラス](../mfc/reference/internal-classes.md)  
 MFC での内部使用。  完全を期すために、このセクションではこれらの内部クラスについて説明しますが、コードで直接使用するためのものではありません。  
  
 [マクロとグローバル](../mfc/reference/mfc-macros-and-globals.md)  
 MFC ライブラリのマクロおよびグローバル関数へのリンクを提供します。  
  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../mfc/reference/structures-styles-callbacks-and-message-maps.md)  
 MFC ライブラリで使用する構造体、スタイル、コールバック関数、およびメッセージ マップへのリンクを提供します。  
  
 [MFC ウィザードとダイアログ ボックス](../mfc/reference/mfc-wizards-and-dialog-boxes.md)  
 Visual Studio の MFC アプリケーションを作成するための機能のガイドです。  
  
 [Working with Resource Files](../mfc/working-with-resource-files.md)  
 リソース ファイルを使用して、UI の文字列やダイアログ ボックスのレイアウトなどの静的ユーザー インターフェイスのデータを管理する方法。  
  
## 関連項目  
 [階層図カテゴリ](../Topic/Hierarchy%20Chart%20Categories.md)  
 カテゴリ別の MFC 階層図を示します。  
  
 [ATL\/MFC の共有クラス](../atl-mfc-shared/atl-mfc-shared-classes.md)  
 MFC と ATL で共有されるクラスへのリンクを提供します。  
  
 [MFC のサンプル](../top/visual-cpp-samples.md)  
 MFC の使い方を示すサンプルへのリンクを提供します。  
  
 [Visual C\+\+ Libraries Reference](http://msdn.microsoft.com/ja-jp/fec23c40-10c0-4857-9cdc-33a3b99b30ae)  
 Visual C\+\+ に用意されているさまざまなライブラリへのリンクがあります。ATL、MFC、OLE DB の各テンプレート、C ランタイム ライブラリ、および標準 C\+\+ ライブラリが含まれます。  
  
 [Visual Studio でのデバッグ](../Topic/Debugging%20in%20Visual%20Studio.md)  
 Visual Studio デバッガーを使用してアプリケーションやストアド プロシージャの論理エラーを修正する方法を説明するトピックへのリンクがあります。  
  
## 参照  
 [MFC と ATL](../mfc/mfc-and-atl.md)