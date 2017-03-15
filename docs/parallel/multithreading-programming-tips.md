---
title: "マルチスレッド: プログラミングのヒント | Microsoft Docs"
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
  - "アクセス制御 [C++], マルチスレッド"
  - "通信 [C++], スレッド間の"
  - "クリティカル セクション [C++]"
  - "ハンドル マップ [C++]"
  - "マルチスレッド処理 [C++], プログラミングに関するヒント"
  - "非 MFC スレッド [C++]"
  - "オブジェクト [C++], 複数のスレッド"
  - "プログラミング [C++], マルチスレッド"
  - "同期 [C++], マルチスレッド"
  - "スレッド処理 [C++], 推奨される手順"
  - "スレッド処理 [MFC], プログラミングに関するヒント"
  - "トラブルシューティング [C++], マルチスレッド"
  - "ウィンドウ ハンドルの割り当て [C++]"
ms.assetid: ad14cc70-c91c-4c24-942f-13a75e58bf8a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# マルチスレッド: プログラミングのヒント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マルチスレッド アプリケーションでデータにアクセスするときは、シングルスレッドの場合より慎重に行う必要があります。  マルチスレッド アプリケーションでは、複数のスレッドがそれぞれ個別に同時に実行されるので、アルゴリズムやデータに関して、複数のスレッドで同じデータが使われることを考慮する必要があります。  このトピックでは、MFC \(Microsoft Foundation Class\) ライブラリを使用してマルチスレッド アプリケーションを開発する場合にこのような問題を回避する手法について説明します。  
  
-   [複数のスレッドからのオブジェクトへのアクセス](#_core_accessing_objects_from_multiple_threads)  
  
-   [非 MFC スレッドからの MFC オブジェクトのアクセス](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
-   [ウィンドウ ハンドルのマップ](#_core_windows_handle_maps)  
  
-   [スレッド間通信](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> 複数のスレッドからのオブジェクトへのアクセス  
 サイズおよびパフォーマンス上の理由により、MFC オブジェクトのスレッドの安全性は、オブジェクト レベルでは保証されず、クラス レベルでしか保証されません。  つまり、2 つの異なるスレッドで 2 つの異なる `CString` オブジェクトを操作することはできますが、2 つの異なるスレッドで同じ `CString` オブジェクトを操作することはできません。  複数のスレッドで 1 つのオブジェクトを操作する必要があるときは、Win32 のクリティカル セクションなどの同期機構を使ってアクセスを保護します。  クリティカル セクションなどの関連オブジェクトの詳細については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353)」を参照してください。  
  
 クラス ライブラリは内部的にクリティカル セクションを使って、デバッグ メモリの割り当てなどが使うグローバル データ構造を保護しています。  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> 非 MFC スレッドからの MFC オブジェクトのアクセス  
 [CWinThread](../mfc/reference/cwinthread-class.md) オブジェクトを使わずにスレッドを作成したマルチスレッド アプリケーションでは、作成したスレッドから MFC オブジェクトにアクセスできません。  つまり、MFC オブジェクトにセカンダリ スレッドからアクセスするには、「[マルチスレッド : ユーザー インターフェイス スレッドの生成](../parallel/multithreading-creating-user-interface-threads.md)」または「[マルチスレッド : ワーカー スレッドの生成](../parallel/multithreading-creating-worker-threads.md)」で説明した方法のいずれかを使用してセカンダリ スレッドを作成する必要があります。  ほかの方法では、マルチスレッド アプリケーションの実行に必要な内部変数をクラス ライブラリで初期化できません。  
  
##  <a name="_core_windows_handle_maps"></a> ウィンドウ ハンドルのマップ  
 通常、スレッドは自分自身が作成した MFC オブジェクトしかアクセスできません。  これは、Windows ハンドルの一時マップとパーマネント マップがスレッド ローカル ストレージに保持されており、複数のスレッドから同時にアクセスできないためです。  たとえば、あるワーカー スレッドで計算を行ってから、ドキュメント オブジェクトの `UpdateAllViews`メンバー関数を呼び出して、新しいデータに対するビューの格納先ウィンドウに反映させることはできません。  `CWnd` オブジェクトから `HWND` へのマップはプライマリ スレッドに固有であるからです。  つまり、あるスレッドで Windows ハンドルから C\+\+ オブジェクトへのマップが行われるときに、別のスレッドで同じハンドルを別の C\+\+ オブジェクトにマップが行われることもあります。  あるスレッドで行われた変更は、ほかのスレッドには反映されません。  
  
 この問題を解決する方法はいくつかあります。  第 1 の方法は、ワーカー スレッドに C\+\+ オブジェクトを渡さずに `HWND` などのハンドルを個別に渡す方法です。  ワーカー スレッドは該当する `FromHandle` メンバー関数を呼び出して、一時マップにオブジェクトを登録します。  関数 **Attach** では、オブジェクトをスレッドのパーマネント マップに登録できます。この方法は、オブジェクトがスレッドの消滅後も残存する場合以外は使わないでください  
  
 もう 1 つの方法は、ワーカー スレッドが処理するタスクごとに新しいユーザー定義のメッセージを作成し、このメッセージを **::PostMessage** 関数を使ってアプリケーションのメイン ウィンドウに渡す方法です。  この通信方法は、2 つの異なるアプリケーション間の対話動作に似ています。ただし、2 つのスレッドが同じアドレス空間を共有する点が異なります。  
  
 ハンドルのマップの詳細については、「[テクニカル ノート 3: Windows ハンドルとオブジェクト間のマップ](../mfc/tn003-mapping-of-windows-handles-to-objects.md)」を参照してください。  スレッド ローカル ストレージの詳細については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[Thread Local Storage](http://msdn.microsoft.com/library/windows/desktop/ms686749)」と「[Using Thread Local Storage](http://msdn.microsoft.com/library/windows/desktop/ms686991)」を参照してください。  
  
##  <a name="_core_communicating_between_threads"></a> スレッド間通信  
 MFC には、スレッドからオブジェクトへのアクセスを同期化して、スレッドの安全性を保証するクラスがあります。  これらのクラスの使い方については、「[マルチスレッド : 同期クラスの使用法](../parallel/multithreading-how-to-use-the-synchronization-classes.md)」と「[マルチスレッド : 同期クラスの使い分け](../parallel/multithreading-when-to-use-the-synchronization-classes.md)」を参照してください。  これらのオブジェクトの詳細については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353)」を参照してください。  
  
## 参照  
 [C\+\+ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)