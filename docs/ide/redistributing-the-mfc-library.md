---
title: "MFC ライブラリの再配布 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "MFC, 再配布"
  - "再頒布 (MFC ライブラリを)"
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
caps.latest.revision: 32
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MFC ライブラリの再配布
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC のすべての DLL は共有バージョンの C ランタイム \(CRT\) ライブラリを使用するため、アプリケーションを MFC ライブラリに動的にリンクする場合は、Msvcr100.dll を再配布する必要があります。  また、Mfc100u.dll または Mfc100.dll も再配布する必要があります。  
  
 アプリケーションを MFC と静的にリンクした場合 \(つまり、**\[プロパティ ページ\]** ダイアログ ボックスの **\[全般\]** タブの **\[スタティック ライブラリで MFC を使用する\]** を指定した場合\)、Mfc100u.dll または Mfc100.dll を再配布する必要はありません。  静的リンクはアプリケーションのテストや内部での配置を行う場合でも該当しますが、MFC の再配布にはそれを使用しないことをお勧めします。  Visual C\+\+ ライブラリの配置の推奨される方法については、「[配置方法の選択](../ide/choosing-a-deployment-method.md)」を参照してください。  
  
 アプリケーションで WebBrowser コントロールを実装した MFC クラス \([CHtmlView クラス](../mfc/reference/chtmlview-class.md) や [CHtmlEditView クラス](../mfc/reference/chtmleditview-class.md) など\) を使用する場合は、ターゲット コンピューターのコモン コントロール ファイルが最新になるように、Microsoft Internet Explorer  の最新バージョンをインストールすることもお勧めします。\(少なくとも、Internet Explorer 4.0 以降が必要です\)。Internet Explorer コンポーネントの最小インストールの方法については、マイクロソフト サポート オンラインの 「Article 185375: How To Create a Single EXE Install of Internet Explorer \(記事 185375: Internet Explorer のインストール ファイルである単一の exe ファイルの作成方法\)」を参照してください。  
  
 アプリケーションで MFC データベース クラス \([CRecordset クラス](../Topic/CRecordset%20Class.md)や [CRecordView クラス](../mfc/reference/crecordview-class.md)など\) を使用する場合は、必要な ODBC および ODBC ドライバーを再配布する必要があります。  詳細については、「[データベース サポート ファイルの再頒布](../ide/redistributing-database-support-files.md)」を参照してください。  
  
 MFC アプリケーションが Windows フォーム コントロールを使用している場合は、アプリケーションと共に mfcmifc80.dll を再配布する必要があります。  この DLL は厳密な名前で署名された .NET アセンブリです。アプリケーションと共にアプリケーションのローカル フォルダーに再配布することもできますし、[Gacutil.exe \(グローバル アセンブリ キャッシュ ツール\)](../Topic/Gacutil.exe%20\(Global%20Assembly%20Cache%20Tool\).md) を使用してグローバル アセンブリ キャッシュ \(GAC: Global Assembly Cache\) に配置して再配布することもできます。  
  
 MFC DLL を再配布する場合は、デバッグ バージョンではなく、リテール バージョンを再配布することを確認してください。  DLL のデバッグ バージョンは再配布できません。  MFC DLL の"デバッグ バージョンの名前は、ファイル名の末尾に "d"が付きます \(たとえば、Mfc100d.dll\)。  
  
 MFC ソースを変更し、その MFC DLL をリビルドする場合は、変更後の MFC DLL が Visual Studio にインクルードされている MFC DLL と競合しないように名前を変更する必要があります。  MFC DLL のリビルドおよび名前の変更は、できる限り行わないでください。  詳細については、MFC のテクニカル ノート 33 を参照してください。  
  
 MFC を再配布するには、VCRedist\_*architecture*.exe を使用するか、Visual Studio と共にインストールされるマージ モジュールを使用するか、MFC DLL をアプリケーションと同じフォルダー内に配置します。  MFC の再配布方法の詳細については、「[Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)」を参照してください。  
  
## テクニカル ノート 56: ローカライズされた MFC コンポーネントのインストール  
 MFC ローカリゼーション DLL をインストールしてアプリケーションをローカライズする場合は、再頒布可能マージ ファイル \(.msm\) を使用する必要があります。  たとえば、アプリケーションを x86 コンピューターにローカライズする場合は、Microsoft\_VC100\_MFCLOC\_x86.msm ファイルを x86 コンピューターのインストール パッケージにマージする必要があります。  
  
 再頒布可能 .msm ファイルには、ローカライズに使用される DLL が含まれます。  サポートされているそれぞれの言語に対して、1 つの DLL があります。  これらの DLL は、インストール プロセスによって、ターゲット コンピューターの %windir%\\system32\\ フォルダーにインストールされます。  
  
 MFC アプリケーションのローカライズ方法の詳細については、マイクロソフト サポート オンラインの「[テクニカル ノート 57: MFC コンポーネントのローカライズ](../mfc/tn057-localization-of-mfc-components.md)」および「[文書番号 208983: \[HOWTO\] MFC LOC DLL を使用する方法](http://go.microsoft.com/fwlink/?LinkId=198025)」を参照してください。  
  
 MFC のローカライズ用 DLL を再配布するには、MFC DLL をアプリケーションのローカル フォルダーに配置します。  Visual C\+\+ ライブラリの再配布方法の詳細については、「[Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)」を参照してください。  
  
## 参照  
 [Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)