---
title: "Visual C++ ツールセットで問題を報告する方法 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: ec24a49c-411d-47ce-aa4b-8398b6d3e8f6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 5c6fbfc8699d7d66c40b0458972d8b6ef0dcc705
ms.openlocfilehash: 2ea129ac94cb1ddc7486ba69280dc0390896e088
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset"></a>Visual C++ ツールセットで問題を報告する方法
Visual C++ のコンパイラ、リンカー、その他のツールを使っていて問題が発生した場合は、Microsoft にお知らせください。  
  
 問題についてのご連絡に最適な方法は、発生した問題の説明、プログラムの作成方法の詳細、および弊社のコンピューターで問題を再現するために使うことができるコードを含む、レポートをお送りいただくことです。 この情報があると、短時間で、問題が存在していて、報告者の環境だけの問題ではないことを確認すること、また、コンパイラの他のバージョンに影響があるかどうかを特定して、原因を診断することができます。  
  
 このドキュメントでは、次のことについて説明します。  
  
-   [レポートを準備する方法](#prepare)、および優れたレポートの内容。  
  
-   [レポートを送信する方法](#send)、およびそれぞれの違い。  
  
-   [再現コードを生成する方法](#generate)、および再現コードのさまざまな種類。  
  
 レポートは、Microsoft にとっても他の開発者にとっても重要です。 Visual C++ の向上にご協力いただきありがとうございます。  
  
##  <a name="prepare"></a> レポートを準備する方法  
 完全な情報がないと弊社のコンピューターで問題を再現するのはとても困難なので、質の高いレポートを作成することが重要です。 レポートの質がよいほど、より効果的に問題を再現して診断できます。  
  
 レポートには少なくとも次の情報を含める必要があります。  
  
-   使っているツールセットの完全なバージョン情報。  
  
-   コードをビルドするために使った完全な cl.exe コマンド ライン。  
  
-   発生した問題の詳細な説明。  
  
-   "再現コード" — 問題を再現するソース コード。  
  
 具体的に必要な情報およびそれが見つかる場所については以下で説明します。  
  
### <a name="the-toolset-version"></a>ツールセットのバージョン  
 弊社のコンピューターで同じツールセットに対して再現コードをテストできるように、お使いのツールセットの完全なバージョン情報が必要です。 問題を再現できる場合、この情報を基にして同じ問題が発生するツールセットの他のバージョンを調査できます。  
  
##### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>使っているコンパイラの完全バージョンを報告するには  
  
1.  キーボードの Windows キーを押して、「`Developer Command Prompt`」と入力します。  
  
2.  一致するものの一覧から、使っている Visual Studio のバージョンに対応する**開発者コマンド プロンプト**のバージョンを選びます。  
  
3.  **開発者コマンド プロンプト** コンソールで、`cl /Bv /CLR` コマンドを入力します。  
  
 出力は次のようになります。  
  
```  
C:\Compiler>cl /Bv /CLR  
Microsoft (R) C/C++ Optimizing Compiler Version 18.00.40209  
for Microsoft (R) .NET Framework version 4.00.30319.34014  
Copyright (C) Microsoft Corporation.  All rights reserved.  
  
Compiler Passes:  
 C:\WinCComp\binaries.x86chk\bin\i386\cl.exe:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c1.dll:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c1xx.dll:      Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c2.dll:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\link.exe:      Version 12.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\mspdb120.dll:  Version 12.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\1033\clui.dll: Version 18.00.40209.0  
 Common Language Runtime:                            Version  4.00.30319.34014  
  
cl : Command line error D8003 : missing source filename   
```  
  
 出力全体をコピーして、レポートに貼り付けます。  
  
### <a name="the-command-line"></a>コマンド ライン  
 弊社のコンピューターでコードをまったく同じ方法でビルドできるように、コードのビルドに使った完全なコマンドライン (cl.exe とその引数) が必要です。 これは、特定の引数または引数の組み合わせを使ってビルドしたときにのみ問題が発生する可能性があるので重要です。  
  
 この情報を検索する最適な場所は、問題が発生した直後のビルド ログです。 このようにすると、問題の原因となった可能性があるまったく同じ引数がコマンド ラインに確実に含まれます。  
  
##### <a name="to-report-the-contents-of-the-command-line"></a>コマンド ラインの内容を報告するには  
  
1.  **CL.command.1.tlog** ファイルを探して開きます。 既定では、このファイルは \\...\Visual Studio Version\Projects\SolutionName\ProjectName\Config\ProjectName.tlog\CL.command.1.tlog にあります。  
  
     このファイルで、ソース コード ファイルの名前と、コンパイルに使われたコマンド ライン引数を探します。これらは別々の行になっています。  
  
2.  問題が発生したソース コード ファイルの名前を含む行を探します。その下の行には、対応する cl.exe コマンドと引数が含まれています。  
  
 コマンド ライン全体をコピーして、レポートに貼り付けます。  
  
### <a name="a-description-of-the-problem"></a>問題の説明  
 弊社のコンピューターで同じ結果を見ていることを確認できるように、問題の詳細な説明が必要です。また、実行しようとしていたこと、および予想された結果をお知らせいただくと、役に立つ場合があります。  
  
 ツールセットで表示された正確なエラー メッセージ、再現コードの理解に役立つように、行おうとしていたことの簡単な説明、および発生した問題の診断に役立つ可能性のある他の詳細情報 (見つかった回避策など) を提供してください。 レポートの別の場所にある情報を繰り返し記載しないでください。  
  
### <a name="the-repro"></a>再現コード  
 こちらのコンピューターでエラーを再現できるように、発生した問題がわかる自己完結型のソース コード例である再現コードが必要です。 発生した問題の種類により、レポートに含める必要がある再現コードの種類が決まります。 適切な再現コードがないと、調査するものがありません。  
  
 短い自己完結型の再現コードはレポート テキストに直接含めることができますが、大きなソース コード再現コードの場合はレポートに添付する必要があります。 1 つのソース コード ファイルにまとめることのできない再現手順は、すべてのファイルを含むディレクトリを .zip ファイルなどに圧縮することでパッケージ化し、レポートに添付する必要があります。 シナリオに固有のその他の詳細情報は、ソース コードではなく、常にレポート テキストに含める必要があります。  
  
 弊社に提供できる最善の種類の再現コードは、*最小限の再現コード*です。 これは、問題を再現するのに十分なコードだけを含む、ユーザー ヘッダーを参照していない、自己完結型の単一のソース コード ファイルです。 この形式の再現コードを提供できる場合は、レポートにソース コード ファイルを添付するだけで十分です。  
  
 依存関係のない最小限の再現コードに問題をまとめることができない場合は、以下の説明を参考にして、レポートに含める必要がある再現コードの種類を決定してください。  
  
#### <a name="frontend-parser-crash"></a>フロントエンド (パーサー) のクラッシュ  
 フロントエンドのクラッシュは、コンパイラの解析フェーズの間に発生します。 通常、コンパイラは、[致命的なエラー C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) を出力し、エラーが発生したソース コード ファイルと行番号を参照します。ファイル msc1.cpp が言及されていることがよくありますが、この詳細は無視してかまいません。  
  
 この種のクラッシュの場合は、[前処理済み再現コード](#preprocessed_repro)を提供してください。  
  
 この種のクラッシュに対するコンパイラ出力の例を次に示します。  
  
```  
SandBoxHost.cpp  
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):  
        fatal error C1001: An internal error has occurred in the compiler.  
(compiler file 'msc1.cpp', line 1369)  
To work around this problem, try simplifying or changing the program near the  
        locations listed above.  
Please choose the Technical Support command on the Visual C++  
Help menu, or open the Technical Support help file for more information  
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):  
        note: This diagnostic occurred in the compiler generated function  
        'void Microsoft::Ceres::Common::Tools::Sandbox::SandBoxedProcess::Dispose(bool)'  
Internal Compiler Error in d:\o\dev\otools\bin\x64\cl.exe.  You will be prompted  
        to send an error report to Microsoft later.  
INTERNAL COMPILER ERROR in 'd:\o\dev\otools\bin\x64\cl.exe'  
    Please choose the Technical Support command on the Visual C++  
    Help menu, or open the Technical Support help file for more information   
```  
  
####  <a name="backend_crash"></a> バックエンド (コード生成) のクラッシュ  
 バックエンドのクラッシュは、コンパイラのコード生成フェーズの間に発生します。 通常、コンパイラは、[致命的なエラー C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) を出力し、問題に関連するソース コード ファイルと行番号を参照していない場合があります。ファイル compiler\utc\src\p2\main.c が言及されていることがよくありますが、この詳細は無視してかまいません。  
  
 この種のクラッシュの場合は、リンク時のコード生成 (LTCG) を使っている場合は[リンク再現コード](#link_repro)を、使っていない場合は[前処理済み再現コード](#preprocessed_repro)を提供してください。 LTGC は、`/GL` コマンド ライン引数を cl.exe に指定することによって有効になります。  
  
 LTCG を使って**いない**場合のこの種のクラッシュに対するコンパイラ出力の例を次に示します。 このようなコンパイラ出力の場合は、[前処理済み再現コード](#preprocessed_repro)を提供する必要があります。  
  
```  
repro.cpp  
\\officefile\public\tadg\vc14\comperror\repro.cpp(13) : fatal error C1001:  
        An internal error has occurred in the compiler.  
(compiler file 'f:\dd\vctools\compiler\utc\src\p2\main.c', line 230)  
To work around this problem, try simplifying or changing the program near the  
        locations listed above.  
Please choose the Technical Support command on the Visual C++  
Help menu, or open the Technical Support help file for more information  
INTERNAL COMPILER ERROR in  
        'C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\cl.exe'  
    Please choose the Technical Support command on the Visual C++  
    Help menu, or open the Technical Support help file for more information  
```  
  
 **内部コンパイラ エラー**で始まる行において、cl.exe ではなく link.exe が言及されている場合は、LTCG が有効になっていたので、[リンク再現手順](#link_repro)を提供する必要があります。 コンパイラのエラー メッセージから LTCG が有効になっていたどうかはっきりわからない場合は、前の手順で `/GL` コマンド ライン引数に対するビルド ログからコピーしたコマンド ライン引数を調べることが必要な場合があります。  
  
#### <a name="linker-crash"></a>リンカーのクラッシュ  
 リンカーのクラッシュは、コンパイラが実行された後のリンク フェーズ中に発生します。 通常、リンカーは[リンカー ツール エラー LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md) を出力します。  
  
> [!NOTE]
>  出力が C1001 またはリンク時コード生成に関するものである場合は、「[バックエンド (コード生成) のクラッシュ](#backend_crash)」で詳細をご覧ください。  
  
 この種のクラッシュの場合は、[リンク再現手順](#link_repro)を提供してください。  
  
 この種のクラッシュに対するコンパイラ出力の例を次に示します。  
  
```  
z:\foo.obj : error LNK1000: Internal error during IMAGE::Pass2  
  
  Version 14.00.22816.0  
  
  ExceptionCode            = C0000005  
  ExceptionFlags           = 00000000  
  ExceptionAddress         = 00007FF73C9ED0E6 (00007FF73C9E0000)  
        "z:\tools\bin\x64\link.exe"  
  NumberParameters         = 00000002  
  ExceptionInformation[ 0] = 0000000000000000  
  ExceptionInformation[ 1] = FFFFFFFFFFFFFFFF  
  
CONTEXT:  
  
  Rax    = 0000000000000400  R8     = 0000000000000000  
  Rbx    = 000000655DF82580  R9     = 00007FF840D2E490  
  Rcx    = 005C006B006F006F  R10    = 000000655F97E690  
  Rdx    = 000000655F97E270  R11    = 0000000000000400  
  Rsp    = 000000655F97E248  R12    = 0000000000000000  
  Rbp    = 000000655F97EFB0  E13    = 0000000000000000  
  Rsi    = 000000655DF82580  R14    = 000000655F97F390  
  Rdi    = 0000000000000000  R15    = 0000000000000000  
  Rip    = 00007FF73C9ED0E6  EFlags = 0000000000010206  
  SegCs  = 0000000000000033  SegDs  = 000000000000002B  
  SegSs  = 000000000000002B  SegEs  = 000000000000002B  
  SegFs  = 0000000000000053  SegGs  = 000000000000002B  
  Dr0    = 0000000000000000  Dr3    = 0000000000000000  
  Dr1    = 0000000000000000  Dr6    = 0000000000000000  
  Dr2    = 0000000000000000  Dr7    = 0000000000000000  
```  
  
 インクリメンタル リンクが有効になっていて、初期リンクつまり後続のインクリメンタル リンクの基になっている最初のフル リンクの後でのみクラッシュが発生する場合は、初期リンクが完了した後で変更されたソース ファイルに対応するオブジェクト (.obj) ファイルとライブラリ (.lib) ファイルのコピーも提供してください。  
  
#### <a name="bad-code-generation"></a>不正なコードの生成  
 不正なコードが生成されることはまれですが、コンパイラが誤って不適切なコードを生成し、アプリケーションがコンパイル時にこの問題を検出せずに実行時にクラッシュすると発生します。 発生している問題が不正なコードの生成の結果であると考えられる場合は、[バックエンド (コード生成) のクラッシュ](#backend_crash)と同じようにレポートを処理してください。  
  
 この種のクラッシュの場合は、リンク時のコード生成 (LTCG) を使っている場合は[リンク再現コード](#link_repro)を、使っていない場合は[前処理済み再現コード](#preprocessed_repro)を提供してください。 LTGC は、`/GL` コマンド ライン引数を cl.exe に指定することによって有効になります。  
  
##  <a name="send"></a> レポートを送信する方法  
 レポートを提出するには複数の方法があります。 Microsoft Connect でのバグの報告、メールでの送信、Visual Studio に組み込まれている問題の報告ツールの使用などを使うことができます。 レポートに最適な選択肢は、発生した問題の種類、レポートを調査するエンジニアとの連絡方法、進捗状況を追跡するかどうか、コミュニティとレポートを共有するかどうかによって異なります。  
  
> [!NOTE]
>  レポートの送信方法に関係なく、Microsoft はお客様のプライバシーを尊重します。 お客様から送信していただいたデータの扱いについて詳しくは、「[Microsoft Visual Studio 製品ファミリのプライバシーに関する声明](https://www.visualstudio.com/dn948229)」をご覧ください。  
  
### <a name="file-a-bug-on-microsoft-connect"></a>Microsoft Connect でバグを報告する  
 Microsoft Connect ([connect.microsoft.com](http://connect.microsoft.com)) は、ユーザー コミュニティが Microsoft 製品を構築するチームと直接連絡するための方法です。 Connect では、新しいバグの報告や機能の要求、コミュニティによって報告された他のバグや行われた要求の表示、自分にとって最も重要なものの表明などを行うことができます。  
  
 レポートを Visual Studio のコミュニティと共有し、その進捗状況を公に追跡したい場合は、Connect で問題を報告するのが最善の方法です。レポートを共有すると、他のユーザーから、回避策や、問題の診断に役立つ追加情報が提供されることがあります。 フォームを送信する前にレポートの公開設定をプライベートにするだけで、レポートを非公開にしたい場合でも (レポートのコードを共有できない場合など)、Connect を使うことができます。  
  
-   [Microsoft Connect: Visual Studio 2015 Update 3 での問題を報告する](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6493)  
  
-   [Microsoft Connect: Visual Studio 2015 Update 2 での問題を報告する](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6406)  
  
-   [Microsoft Connect: Visual Studio 2015 Update 1 での問題を報告する](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6326)  
  
-   [Microsoft Connect: Visual Studio 2015 での問題を報告する](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6240)  
  
 [Visual Studio および .NET Framework のフィードバック](https://connect.microsoft.com/VisualStudio/feedback/LoadSubmitFeedbackForm)に関する Connect ページのドロップダウンで製品を選ぶことにより、他の Visual Studio および .Net Framework の製品についての問題を報告できます。  
  
### <a name="send-an-email"></a>メールを送信する  
 メールは、Visual C++ チームにレポートを直接送るもう 1 つの方法です。アドレスは [compilercrash@microsoft.com](mailto:compilercrash@microsoft.com) です。  
  
 メールによる問題の報告は、Microsoft Connect のような充実したコミュニティは利用できませんが、再現コードが大きい場合に適していることがあります。 また、作業環境がインターネットに接続されていない場合、または他の理由で Microsoft Connect を使用できない場合は、メールが最善または唯一のオプションになります。  
  
 レポートをメールで送信する場合は、メール メッセージの本文として次のテンプレートを使用できます。 ソース コードなどの情報をメール本文に含めない場合は、忘れずにソース コード ファイルや他のファイルを添付してください。  
  
```  
To: compilercrash@microsoft.com  
Subject: Visual C++ Error Report  
-----  
  
Compiler version:  
  
CL.EXE command line:  
  
Problem description:  
  
Source code and repro steps:  
  
```  
  
### <a name="use-the-report-a-problem-tool"></a>問題の報告ツールを使う  
 Visual Studio の問題の報告ツールを使うと、Visual Studio のユーザーはわずか数クリックでさまざまな問題を報告できます。 IDE を終了することなく、簡単なフォームを使って、発生している問題についての詳細な情報を指定し、レポートを送信できます。  
  
 問題の報告ツールを使って問題を報告することは、このドキュメントで説明されているツールセットの問題の種類についてはあまり行われません。しかしながら、状況に適している場合はこのオプションを選ぶことができます。  
  
> [!TIP]
>  Visual Studio で発生する可能性がある、ツールセットに関係しない他の種類の問題 (たとえば、UI の問題、IDE の機能の不具合、一般的なクラッシュなど) の場合は、問題の報告ツールを使うのが特に適しています。このツールのスクリーンショット機能や、発生した問題をもたらした UI 操作を記録する機能が役に立ちます。 これらの他の種類のエラーを報告するには Microsoft Connect も適していますが、問題の報告ツールのような追加機能はありません。 これらの他の種類のエラーの報告には、compilercrash@microsoft.com へのメール送信は使わないでください。  
  
##  <a name="generate"></a> 再現手順の生成  
 再現コードは、報告する問題を実際に示す完全な自己完結型のコード例です。 再現コードはコード スニペットでは**ありません**。ビルドして実行する完全な例 (または、報告している問題によって生成されるエラー以外) でなければなりません。 標準ヘッダーの場合であっても、必要な #include ディレクティブをすべて含む必要があります。  
  
 さらに、適切な再現コードとは次のようなものです。  
  
-   **最小限である**。 再現手順は、発生した問題を正確に再現しながら、可能な限り小さいものでなければなりません。 再現コードは複雑あるいは現実的である必要はありません。シンプルで的を射た再現コードの方が優れています。 動作するコードの反例を含む必要はありませんが、役に立つなら含んでいても構いません。問題の原因の例であるコードだけが必要です。  
  
-   **自己完結的である**。 再現手順には、必要のない依存関係を含めないようにする必要があります。 サード パーティ製のライブラリがなくても問題を再現できる場合は、使わずに再現してください。 ライブラリ コードがなくても問題を再現できる場合は (`std::out`、`printf()` はあってもかまいません)、使わずに再現してください。 問題の可能性のある原因として考える必要のあるコードの量を減らすことは、調査するときにとても役に立ちます。  
  
-   **最新バージョンのコンパイラが対象である**。 可能なかぎり、再現手順では最新バージョンのツールセットを使う必要があります。 古いバージョンのツールセットでまだ発生している問題でも、ほとんどの場合は、新しいバージョンで修正されています。  
  
-   **他のコンパイラで確認されている** (関連する場合)。 移植可能な C++ コードに関係のある再現手順は、可能であれば、他のコンパイラで動作を確認する必要があります。  
  
     この手順は、MSVC が Clang および GCC と一致しないときにコードが正しいかどうかを判断するため、または MSVC、Clang、GCC が一致するときにコードが正しくないかどうかを判断するために役に立ちます。  
  
 異なる種類の問題の報告に使うさまざまな種類の再現コードを生成する手順を次に示します。  
  
###  <a name="preprocessed_repro"></a> 前処理済み再現コード  
 前処理済みの再現コードは、問題を示す単一のソース ファイルであり、元のソース ファイルを処理することによって C プリプロセッサの出力から生成されます。 この処理では、インクルードされているヘッダーがインライン化されて他のソース ファイルとヘッダー ファイルへの依存関係が削除され、ローカル環境に依存する可能性のあるマクロ、#ifdefs、その他のプリプロセッサ コマンドも解決されます。  
  
> [!NOTE]
>  問題の原因が標準ライブラリの実装におけるバグの可能性がある場合、通常、問題が解決済みかどうかを確認するために最新の作業中の実装に置き換えるので、前処理済みの再現コードは最も役に立ちません。 この場合は、再現コードを前処理しないでください。また、問題を 1 つのソース ファイルに減らすことができない場合は、コードを .zip ファイルなどにパッケージ化するか、IDE プロジェクトの再現コード (後の「[その他の再現コード](#other_repros)」を参照) の使用を検討してください。  
  
##### <a name="to-preprocess-a-source-code-file"></a>ソース コード ファイルを前処理するには  
  
1.  キーボードの Windows キーを押して、「`Developer Command Prompt`」と入力します。  
  
2.  一致するものの一覧から、使っている Visual Studio のバージョンに対応する**開発者コマンド プロンプト**のバージョンを選びます。  
  
3.  **開発者コマンド プロンプト** コンソール ウィンドウで、`cl /P argumentsfilename.cpp` コマンドを入力します。  
  
 ファイルを前処理した後は (<ファイル名>.i)、前処理済みファイルを使って問題が再現することを確認します。 `/TP` コマンド ライン引数を使ってプリプロセッサ ステップをスキップするよう cl.exe に指示し、通常どおりにコンパイルを試みます。  
  
##### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>前処理済みファイルでエラーが再現することを確認するには  
  
1.  キーボードの Windows キーを押して、「`Developer Command Prompt`」と入力します。  
  
2.  一致するものの一覧から、使っている Visual Studio のバージョンに対応する**開発者コマンド プロンプト**のバージョンを選びます。  
  
3.  **開発者コマンド プロンプト** コンソール ウィンドウで、`cl arguments /TP filename.i` コマンドを入力します。  
  
4.  問題が再現することを確認します。  
  
 最後に、レポートにこの再現コードを添付します。  
  
###  <a name="link_repro"></a> リンク再現コード  
 リンク再現コードは、ビルド成果物を含む 1 つのディレクトリであり、リンク時コード生成 (LTCG) が関係するバックエンド クラッシュやリンカー クラッシュなど、リンク時に発生する問題を全体として再現します。含まれるビルド成果物は、問題を再現できるようにリンカー入力として必要なものです。 リンク再現コードは、リンカーによって提供される機能を使って簡単に作成できます。  
  
##### <a name="to-generate-a-link-repro"></a>リンク再現コードを生成するには:  
  
1.  コマンド プロンプトを開き、`mkdir directory` コマンドを入力して、リンク再現コード用のディレクトリを作成します。  
  
2.  `set link_repro=directory` コマンドを入力して、link_repro 環境変数に作成したディレクトリを設定します。  
  
3.  Visual Studio 内からビルドを実行する場合は、`devenv` コマンドを入力することで、コマンド プロンプトから起動します。 これにより、link_repro 環境変数の値を Visual Studio で認識できるようになります。  
  
4.  アプリケーションをビルドし、予想される問題が発生することを確認します。  
  
5.  手順 3 で Visual Studio を起動した場合は閉じます。  
  
6.  `set link_repro=` コマンドを入力して、link_repro 環境変数をクリアします。  
  
 最後に、ディレクトリ全体を .zip ファイルなどに圧縮することで再現コードをパッケージ化し、レポートに添付します。  
  
###  <a name="other_repros"></a> その他の再現コード  
 1 つのソース ファイルまたは前処理済み再現コードに問題をまとめることができず、問題にリンク再現コードが必要ない場合は、IDE プロジェクトを調査できます。 プロジェクト内のコードは最小限であり、このドキュメントのすべてのガイダンスが同じように適用されます。  
  
 最小限の IDE プロジェクトとして再現コードを作成し、ディレクトリ構造全体を .zip ファイルなどに圧縮してパッケージ化した後、レポートに添付します。
