---
title: "スタティック ライブラリ (C + + CX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a68475447ed520298b0eab7949386c2e8d078ac6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="static-libraries-ccx"></a>スタティック ライブラリ (C++/CX)
ユニバーサル Windows プラットフォーム アプリで使用されるスタティック ライブラリは、STL 型、およびユニバーサル Windows プラットフォーム アプリのプラットフォームから除外されていない Win32 Api への呼び出しを含む、ISO 標準の C++ コードを含めることができます。 スタティック ライブラリは、Windows ランタイム コンポーネントを処理し、特定の制限の Windows ランタイム コンポーネントを作成します。  
  
## <a name="creating-static-libraries"></a>スタティック ライブラリの作成  
  
#### <a name="to-create-a-static-library-for-use-in-a-universal-windows-platform-app"></a>ユニバーサル Windows プラットフォーム アプリで使用するためのスタティック ライブラリを作成するには  
  
1.  メニュー バーで、次のように選択します**ファイル** > **新規** > **プロジェクト** > **空のスタティック ライブラリ**。ユニバーサル windows プラットフォーム アプリ。  
  
2.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]**をクリックします。 **プロパティ** ダイアログ ボックスで、**構成プロパティ** > **全般**にユニバーサル Windows プラットフォーム アプリのサポートを設定 ページで、 **はい**です。  
  
3.  **構成プロパティ** > **C/C++**  ページで、設定**消費**Windows ランタイム**拡張子**に**はい (/ZW)**です。  
  
 ユニバーサル Windows プラットフォーム アプリの除外されている Win32 API への呼び出しを行う場合に新規のスタティック ライブラリをコンパイルするときにコンパイラによってエラー C3861「識別子が見つかりませんでした」が発生 Windows ランタイムのサポートされている別の方法を探すを参照してください。 [Windows ストア アプリでの Windows Api に代わる方法](http://msdn.microsoft.com/en-us/75568012-61e0-41cc-a4df-c698f54f21ec)です。  
  
 C++ スタティック ライブラリ プロジェクトをユニバーサル Windows プラットフォーム アプリ ソリューションに追加する場合は、ユニバーサル Windows プラットフォームのサポート プロパティに設定するように、ライブラリ プロジェクトのプロパティの設定を更新する必要があります**はい**です。 この設定がなくてもコードはビルドとリンクを実行しますが、 [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)]アプリケーションの検証を試みるとエラーが発生します。 スタティック ライブラリは、そのライブラリを利用するプロジェクトと同じコンパイラ設定でコンパイルする必要があります。  
  
 `ref` パブリック クラス、パブリック インターフェイス クラス、またはパブリック値クラスを作成するスタティック ライブラリを使用すると、リンクは次の警告を出します。  
  
> **警告 LNK4264:**をスタティック ライブラリ; に/ZW でコンパイルされたオブジェクト ファイルをアーカイブには、Windows ランタイム型を作成するときに推奨されないことを Windows ランタイム メタデータを含むスタティック ライブラリとリンクに注意してください。  
  
 スタティック ライブラリは、ライブラリ自体の外部で使用される Windows ランタイム コンポーネントを生成しない場合のみに安全に、警告を無視できます。 ライブラリが、自らが定義したコンポーネントを利用していない場合、パブリック メタデータに型情報が含まれている状況でも、リンカーは実装を最適化できます。 このことは、スタティック ライブラリ内のパブリック コンポーネントはコンパイルされるが、実行時にアクティブにならないことを意味します。 このため、ダイナミック リンク ライブラリ (DLL) で他のコンポーネントまたはアプリケーションで消費される Windows ランタイム コンポーネントを実装しなければなりません。  
  
## <a name="see-also"></a>参照  
 [スレッドとマーシャ リング](../cppcx/threading-and-marshaling-c-cx.md)