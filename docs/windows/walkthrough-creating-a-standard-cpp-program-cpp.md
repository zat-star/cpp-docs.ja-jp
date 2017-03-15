---
title: "チュートリアル: Win32 コンソール プログラムの作成 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "vcfirstapp"
  - "vccreatefirst"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド ライン アプリケーション [C++], 標準"
  - "標準アプリケーション [C++]"
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
caps.latest.revision: 36
caps.handback.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# チュートリアル: Win32 コンソール プログラムの作成 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio の Visual C\+\+ の統合開発環境 \(IDE: Integrated Development Environment\) を使用して、標準 C\+\+ プログラムを作成できます。  このチュートリアルの手順に従って、プロジェクトを作成し、プロジェクトに新しいファイルを追加してから、ファイルを変更して C\+\+ コードを追加できます。次に、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] を使用してプログラムをコンパイルし、実行できます。  
  
 独自の C\+\+ プログラムを入力するか、サンプル プログラムを使用できます。  このチュートリアルのサンプル プログラムは、コンソール アプリケーションです。  このアプリケーションでは、標準テンプレート ライブラリ \(STL: Standard Template Library\) の `set` コンテナーを使用します。  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] は、2 段階名前検索、例外指定、およびエクスポートという主な例外を除き、2003 C\+\+ 標準に従います。  また、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] では、ラムダ、auto、static\_assert、rvalue 参照、extern テンプレートなど、いくつかの C\+\+0x 機能がサポートされます。  
  
> [!NOTE]
>  標準への準拠が必要な場合は、**\/Za** コンパイラ オプションを使用して、標準に対する Microsoft 拡張機能を無効にします。  詳細については、「[\/Za、\/Ze \(言語拡張機能の無効化\)](../build/reference/za-ze-disable-language-extensions.md)」を参照してください。  
  
## 必須コンポーネント  
 このチュートリアルを完了するには、C\+\+ 言語の基本を理解している必要があります。  
  
### プロジェクトを作成してソース ファイルを追加するには  
  
1.  **\[ファイル\]** メニューの **\[新規作成\]** をポイントして **\[プロジェクト\]** をクリックすることにより、プロジェクトを作成します。  
  
2.  **\[Visual C\+\+\]** プロジェクトの種類ペインで、**\[Win32\]** をクリックし、次に **\[Win32 コンソール アプリケーション\]** をクリックします。  
  
3.  プロジェクトの名前を入力します。  
  
     既定では、プロジェクトを含むソリューションはプロジェクトと同じ名前になりますが、別の名前を入力してもかまいません。  プロジェクトの場所として別の場所を入力することもできます。  
  
     **\[OK\]** をクリックして、プロジェクトを作成します。  
  
4.  **Win32 アプリケーション ウィザード**で、**\[次へ\]** をクリックし、**\[空のプロジェクト\]** をクリックし、**\[完了\]** をクリックします。  
  
5.  **ソリューション エクスプローラー**が表示されない場合は、**\[表示\]** メニューの **\[ソリューション エクスプローラー\]** をクリックします。  
  
6.  次のように、プロジェクトに新しいソース ファイルを追加します。  
  
    1.  **ソリューション エクスプローラー**で、**\[ソース ファイル\]** フォルダーを右クリックし、**\[追加\]** をポイントして、**\[新しい項目\]** をクリックします。  
  
    2.  **\[コード\]** ノードの **\[C\+\+ ファイル \(.cpp\)\]** をクリックし、ファイル名を入力して **\[追加\]** をクリックします。  
  
     **ソリューション エクスプローラー**の \[ソース ファイル\] フォルダーに .cpp ファイルが表示され、ファイルが Visual Studio エディターに開かれます。  
  
7.  エディターのファイルで、標準 C\+\+ ライブラリを使用する有効な C\+\+ プログラムを入力するか、サンプル プログラムをコピーしてファイルに貼り付けます。  
  
     たとえば、ヘルプの標準テンプレート ライブラリのサンプルの 1 つである [set::find](../misc/set-find-stl-samples.md) サンプル プログラムを使用できます。  
  
     サンプル プログラムを使用する場合は、`using namespace std;` ディレクティブに注意してください。  このディレクティブによって、プログラムで `cout` および `endl` を使用でき、完全修飾名 \(`std::cout` および `std::endl`\) は必要ありません。  
  
8.  ファイルを保存します。  
  
9. **\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  
  
     **出力**ウィンドウに、ビルド ログの場所やビルドの状態を示すメッセージなど、コンパイルの進行状況に関する情報が表示されます。  
  
10. **\[デバッグ\]** メニューの **\[デバッグなしで開始\]** をクリックします。  
  
     サンプル プログラムを使用した場合、コマンド ウィンドウが表示され、コマンドセット内に特定の整数があるかどうかが示されます。  
  
## 次の手順  
 **前へ:** [Creating Command\-Line Applications \(C\+\+\)](http://msdn.microsoft.com/ja-jp/2505d9ed-aca4-426a-9071-078a2d707254) **次へ:** [チュートリアル: コマンド ラインでのネイティブ C\+\+ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)  
  
## 参照  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ja-jp/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)