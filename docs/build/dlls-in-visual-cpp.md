---
title: "Visual C++ の DLL | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL [C++]"
  - "DLL [C++], 概要 (DLLs の)"
  - "動的リンク [C++]"
  - "実行可能ファイル [C++]"
  - "リンク [C++], 動的と静的"
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ の DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイナミック リンク ライブラリ \(DLL\) は、関数とリソースの共有ライブラリとして機能する実行可能ファイルです。  動的リンクは、関数を呼び出すか、別のファイルに格納されたリソースを使用する実行可能ファイルを有効にします。  これらの関数とリソースはコンパイルできるだけでなく、これらを使用する実行可能ファイルとは別に配置することができます。  オペレーティング システムは、実行可能ファイルの読み込み時、または実行時に必要に応じて、DLL を実行可能ファイルのメモリ領域に読み込むことができます。  また、DLL は、実行可能ファイル間で関数とリソースを共有しやすくします。  メモリ内の DLL の内容には、同時に複数のアプリケーションがアクセスできます。  
  
 静的リンクは、.lib ファイル内のすべてのオブジェクト コードを実行可能ファイルにコピーします。  動的リンクには、データ項目または関数を含む DLL の検索と読み込みのために実行時に必要となる情報のみが含まれます。  DLL を作成するときは、この情報を含む .lib ファイルも作成してください。  DLL を呼び出す実行可能ファイルをビルドするときに、リンカーは、.lib ファイルで、エクスポートされたシンボルを使用して、この情報をローダーに格納します。  ローダーが DLL を読み込むと、DLL は実行可能ファイルのメモリ領域にマップされます。  DLL 内の特殊な関数である `DllMain` は、DLL が必要とするすべての初期化を実行するために呼び出されます。  
  
 静的リンクの代わりに動的リンクを使うと、いくつかの利点があります。  DLL を使用すると、メモリ領域を節約し、スワップを低減できます。  複数のアプリケーションが DLL の 1 つのコピーを使用すると、ディスク領域とダウンロードの帯域幅を節約することができます。  DLL は、個別に配置および更新できます。これにより、すべてのコードのリビルドと出荷をしなくても、出荷後のサポートとソフトウェアの更新プログラムを提供することができます。  DLL は、ロケール固有のリソースを指定する便利な方法です。多言語のプログラムをサポートし、アプリケーションの各国語バージョンを簡単に作成することができます。  
  
 次のトピックでは、DLL のプログラミン方法について詳しく説明します。  
  
## このセクションの内容  
 [チュートリアル: ダイナミック リンク ライブラリの作成と使用 \(C\+\+\)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
 Visual Studio を使用して DLL を作成および使用する方法について説明します。  
  
 [アプリケーションと DLL の違い](../build/differences-between-applications-and-dlls.md)  
 アプリケーションと DLL の基本的な違いについて説明します。  
  
 [DLL の利点](../build/advantages-of-using-dlls.md)  
 動的リンクの利点について説明します。  
  
 [DLL の種類](../build/kinds-of-dlls.md)  
 ビルドできる各種 DLL に関する情報を提供します。  
  
 [DLL に関してよく寄せられる質問](../build/dll-frequently-asked-questions.md)  
 DLL に関してよく寄せられる質問への回答を示します。  
  
 [DLL と実行形式のリンク](../build/linking-an-executable-to-a-dll.md)  
 DLL との明示的なリンクと暗黙的なリンクについて説明します。  
  
 [DLL の初期化](../build/initializing-a-dll.md)  
 DLL の読み込み時に実行する必要がある、メモリの割り当てなどの DLL の初期化コードについて説明します。  
  
 [ランタイム ライブラリの動作](../build/run-time-library-behavior.md)  
 ランタイム ライブラリで DLL の起動処理をどのように実行するかについて説明します。  
  
 [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
 **LoadLibrary** と `AfxLoadLibrary` を使用して、実行時に DLL と明示的にリンクする方法について説明します。  
  
 [GetProcAddress](../build/getprocaddress.md)  
 **GetProcAddress** を使用して DLL のエクスポート関数のアドレスを取得する方法について説明します。  
  
 [FreeLibrary と AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
 DLL モジュールが不要になったときの **FreeLibrary** と `AfxFreeLibrary` の使い方について説明します。  
  
 [Windows が使用する DLL 検索パス](../build/search-path-used-by-windows-to-locate-a-dll.md)  
 Windows オペレーティング システムがシステム上の DLL を検索するために使用する検索パスについて説明します。  
  
 [MFC と動的にリンクされるレギュラー DLL のモジュール状態](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
 MFC と動的にリンクされるレギュラー DLL のモジュール状態について説明します。  
  
 [拡張 DLL](../build/extension-dlls-overview.md)  
 既存の MFC ライブラリ クラスから派生した再利用可能なクラスを主に実装する DLL について説明します。  
  
 [リソースのみの DLL の作成](../build/creating-a-resource-only-dll.md)  
 アイコン、ビットマップ、文字列、ダイアログ ボックスなどのリソースだけを含む、リソースのみの DLL について説明します。  
  
 [MFC アプリケーションのローカライズされたリソース : サテライト DLL](../build/localized-resources-in-mfc-applications-satellite-dlls.md)  
 混合言語にローカライズされるアプリケーションの作成に役立つ、サテライト DLL のサポートを強化します。  
  
 [インポートとエクスポート](../build/importing-and-exporting.md)  
 アプリケーションへのパブリック シンボルのインポート、または DLL からの関数のエクスポートについて説明します。  
  
 [Active テクノロジと DLL](../build/active-technology-and-dlls.md)  
 オブジェクト サーバーを DLL 内部に実装できます。  
  
 [DLL でのオートメーション](../build/automation-in-a-dll.md)  
 MFC DLL ウィザードの \[オートメーション\] オプションについて説明します。  
  
 [MFC DLL の名前付け規則](../build/naming-conventions-for-mfc-dlls.md)  
 MFC に含まれる DLL やライブラリに適用される一定の名前付け規則について説明します。  
  
 [DLL 関数の Visual Basic アプリケーションからの呼び出し方](../build/calling-dll-functions-from-visual-basic-applications.md)  
 Visual Basic アプリケーションから DLL 関数を呼び出す方法について説明します。  
  
## 関連項目  
 [DLL の構成要素としての MFC](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
 MFC ライブラリを Windows ダイナミック リンク ライブラリの一部として使用できるレギュラー DLL について説明します。  
  
 [テクニカル ノート 33: MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)  
 MFC アプリケーションおよび拡張 DLL での MFCxx.dll および MFCxxD.dll \(x は MFC のバージョン番号\) 共有ダイナミック リンク ライブラリの使用について説明します。  
  
 [\(NOTINBUILD\)Visual C\+\+ Programming Methodologies](http://msdn.microsoft.com/ja-jp/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Visual C\+\+ ライブラリに関する概念を説明するトピックや、さまざまなコーディングの技術や技法について説明するトピックへのリンクがあります。