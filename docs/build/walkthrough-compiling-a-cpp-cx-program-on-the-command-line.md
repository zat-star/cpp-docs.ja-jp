---
title: "チュートリアル: をコンパイルする C + + CX プログラムのコマンドラインで |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 677779aa8550869fe0859974b2aa4bbbb1c23d83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル
Windows ランタイムをターゲットにする Visual C++ プログラムを作成して、コマンド ライン上に構築できます。 Visual C++ は Visual C++ コンポーネント拡張 (C++/CX) をサポートしており、Windows ランタイム プログラミング モデルをターゲットにするための追加のタイプとオペレーターがあります。 C++/CX を使って Windows Phone 8.1、Windows Store、および Windows デスクトップのアプリを作成できます。 詳細については、次を参照してください。 [A ツアーの c++ + CX](http://msdn.microsoft.com/magazine/dn166929.aspx)と[ランタイム プラットフォームのコンポーネント拡張](../windows/component-extensions-for-runtime-platforms.md)です。  
  
 このチュートリアルでは、テキスト エディターを使って基本的な C++/CX プログラムを作成し、コマンド ラインでコンパイルします。 (表示されているプログラムをタイプするのではなく、自分の C++/CX プログラムを使用するか、別のヘルプ記事の C++/CX コード サンプルを使用できます。 この手法は UI 要素が含まれていない小さなモジュールをビルドおよびテストするのに便利です。)  
  
> [!NOTE]
>  Visual Studio IDE を使って C++/CX プログラムをコンパイルすることもできます。 IDE には、コマンド ラインでは利用できない、デザイン、デバッグ、エミュレーション、および配置のサポートが含まれているため、Windows ストア アプリをビルドする場合は IDE を使用することをお勧めします。 詳細については、次を参照してください。[基本的な C++ ストア アプリを作成する](http://msdn.microsoft.com/library/windows/apps/dn263168)です。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 C++ 言語の基本を理解している必要があります。  
  
## <a name="compiling-a-ccx-program"></a>C++/CX プログラムのコンパイル  
 C + のコンパイルを有効にする + CX、行う必要があります、 [/ZW](../build/reference/zw-windows-runtime-compilation.md)コンパイラ オプション。 Visual C++ コンパイラは、Windows Runtime をターゲットにする .exe ファイルを生成し、必要なライブラリにリンクします。  
  
#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>コマンド ラインで C++/CX アプリケーションをコンパイルするには:  
  
1.  開く、**開発者コマンド プロンプト**ウィンドウです。 (上、**開始**ウィンドウを開いた**アプリ**です。 開く、 **Visual Studio Tools**お使いの下にあるフォルダー[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]を選択し、**開発者コマンド プロンプト**ショートカットです)。開発者コマンド プロンプト ウィンドウを開く方法の詳細については、次を参照してください。[コマンドラインでビルドの c/c++ コード](../build/building-on-the-command-line.md)です。  
  
     コンピューターのオペレーティング システムと構成によっては、コードを正常にコンパイルするために管理者の資格情報が必要な場合があります。 実行するには、コマンド プロンプト ウィンドウを管理者としてのショートカット メニューを開き、**開発者コマンド プロンプト**を選択し**管理者として実行**です。  
  
2.  コマンド プロンプトで次のように入力します。**メモ帳 basiccx.cpp**です。  
  
     選択**はい**されたら、ファイルを作成します。  
  
3.  メモ帳で、次の行を入力します。  
  
    ```cpp  
    using namespace Platform;  
  
    int main(Platform::Array<Platform::String^>^ args)  
    {  
        Platform::Details::Console::WriteLine("This is a C++/CX program.");  
    }  
  
    ```  
  
4.  メニュー バーで、次のように選択します。**ファイル**、**保存**です。  
  
     Windows ランタイムを使用する Visual C ソース ファイルを作成した[Platform 名前空間](../cppcx/platform-namespace-c-cx.md)名前空間。  
  
5.  コマンド プロンプトで次のように入力します。 **cl/EHsc/ZW basiccx.cpp/link/SUBSYSTEM:CONSOLE**です。 cl.exe コンパイラは、ソース コードを .obj ファイルにコンパイルした後、リンカーを実行して basiccx.exe という名前の実行プログラムを生成します。 (、 [/EHsc](../build/reference/eh-exception-handling-model.md)コンパイラ オプションは C++ 例外処理モデルを指定し、 [/link](../build/reference/link-pass-options-to-linker.md)フラグはコンソール アプリケーションを指定します)。  
  
6.  コマンド プロンプトで、basiccx.exe プログラムを実行する入力**basiccx**です。  
  
     プログラムは、次のテキストを表示して終了します。  
  
    ```Output  
    This is a C++/CX program.  
    ```  
  
## <a name="see-also"></a>参照  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)   
 [コンパイラ オプション](../build/reference/compiler-options.md)