---
title: "C/C++ side-by-side アセンブリのビルド | Microsoft Docs"
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
  - "side-by-side 実行アプリケーション [C++]"
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
caps.latest.revision: 18
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ side-by-side アセンブリのビルド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[side\-by\-side アセンブリ](_win32_side_by_side_assemblies)は、アプリケーションで実行時に使用できるリソース \(DLL のグループ、ウィンドウ クラス、COM サーバー、タイプ ライブラリ、またはインターフェイス\) のコレクションです。  DLL をアセンブリに再パッケージ化する主な利点は、複数のバージョンのアセンブリをアプリケーションで同時に使用できるので、更新リリースがある場合も現在インストールされているアセンブリにサービスを提供できることです。  
  
 Visual C\+\+ アプリケーションは、アプリケーションの異なる部分で 1 つまたは複数の DLL を使用できます。  実行時に、DLL がメイン プロセスに読み込まれ、必要なコードが実行されます。  アプリケーションは、オペレーティング システムに応じて、必要な DLL を検索して、他に読み込む必要のある依存 DLL を識別し、必要な DLL と共にこの依存 DLL を読み込みます。  Windows XP、Windows Server 2003、および Windows Vista より前のバージョンの Windows オペレーティング システムでは、オペレーティング システム ローダーが、アプリケーションのローカル フォルダー、またはシステム パスで指定された他のフォルダーで依存 DLL を検索します。  Windows XP、Windows Server 2003、および Windows Vista では、オペレーティング システム ローダーは、[マニフェスト](http://msdn.microsoft.com/library/aa375365) ファイルを使用した依存 DLL の検索、およびこれらの DLL を含む side\-by\-side アセンブリの検索も行います。  
  
 既定では、DLL が Visual Studio でビルドされると、[アプリケーション マニフェスト](http://msdn.microsoft.com/library/aa374191)は、ID が 2 の RT\_MANIFEST リソースとして DLL に埋め込まれます。  実行可能ファイルと同様に、このマニフェストには、この DLL の他のアセンブリへの依存関係が記述されています。  これは、その DLL が side\-by\-side アセンブリに含まれず、また、この DLL に依存するアプリケーションは、DLL の読み込みにアプリケーション マニフェストを使用しないで、代わりにオペレーティング システム ローダーによってシステム パス上でこの DLL を検索することを前提としています。  
  
> [!NOTE]
>  アプリケーション マニフェストを使用する DLL にとっては、このマニフェストが ID 2 のリソースとして埋め込まれていることが重要です。  DLL が、たとえば、[LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175) 関数を使用して実行時に動的に読み込まれる場合、オペレーティング システム ローダーは、DLL のマニフェストで指定されている依存アセンブリを読み込みます。  DLL の外部アプリケーション マニフェストは、`LoadLibrary` 呼び出しの間はチェックされません。  マニフェストが埋め込まれていない場合、ローダーは、間違ったバージョンのアセンブリを呼び出そうとするか、依存アセンブリの検索に失敗します。  
  
 1 つまたは複数の関連 DLL は、対応する[アセンブリ マニフェスト](http://msdn.microsoft.com/library/aa374219)と共に、side\-by\-side アセンブリに再パッケージ化できます。アセンブリ マニフェストには、このアセンブリを構成するファイルと、このアセンブリの他の side\-by\-side アセンブリへの依存関係が記述されています。  
  
> [!NOTE]
>  アセンブリに DLL が 1 つ含まれている場合は、この DLL にアセンブリ マニフェストを ID が 1 のリソースとして埋め込み、プライベート アセンブリに DLL と同じ名前を指定することをお勧めします。  たとえば、DLL の名前が mylibrary.dll の場合、マニフェスト内の assemblyIdentity \<要素\> で使用される name 属性の値も mylibrary になる場合があります。  場合によっては、ライブラリの拡張子が .dll 以外であるときに \(たとえば MFC ActiveX Controls プロジェクトは .ocx ライブラリを作成する\)、外部アセンブリ マニフェストが作成されます。  この場合、アセンブリとそのマニフェストの名前は、DLL の名前とは別にする必要があります \(たとえば、MyAssembly、MyAssembly.manifest、および mylibrary.ocx\)。  しかし、このような場合でも、このアセンブリの将来の保守コストを下げるために、ライブラリの名前を変更して拡張子 .dll を付け、マニフェストをリソースとして埋め込むことをお勧めします。  オペレーティング システムでプライベート アセンブリを検索する方法の詳細については、「[Assembly Searching Sequence](http://msdn.microsoft.com/library/aa374224)」を参照してください。  
  
 この変更によって、対応する DLL を、[プライベート アセンブリ](_win32_private_assemblies)としてアプリケーション ローカル フォルダーに、または[共有アセンブリ](https://msdn.microsoft.com/en-us/library/aa375996.aspx)として WinSxS アセンブリ キャッシュに配置できます。  この新しいアセンブリが実行時に正常に動作するようにするには、複数の手順を実行する必要があります。「[Guidelines for Creating Side\-by\-side Assemblies](http://msdn.microsoft.com/library/aa375155)」を参照してください。  アセンブリを正しく作成したら、共有アセンブリまたはプライベート アセンブリとして、それに依存するアプリケーションと共に配置できます。  side\-by\-side アセンブリを共有アセンブリとしてインストールする場合は、「[Installing Win32 Assemblies for Side\-by\-Side Sharing on Windows XP](http://msdn.microsoft.com/library/aa369532)」で概説されているガイドラインに従うか、[マージ モジュール](http://msdn.microsoft.com/library/aa369820)を使用できます。  side\-by\-side アセンブリをプライベート アセンブリとしてインストールする場合は、このアセンブリが実行時にローダーによって検出されるように、対応する DLL、リソース、およびアセンブリ マニフェストを、インストール プロセスの一環としてインストール先のコンピューターのアプリケーション ローカル フォルダーにコピーするだけで済む可能性があります \(「[Assembly Searching Sequence](http://msdn.microsoft.com/library/aa374224)」を参照してください\)。  他に、[Windows インストーラー](http://msdn.microsoft.com/library/cc185688)を使用し、「[Installing Win32 Assemblies for the Private Use of an Application on Windows XP](http://msdn.microsoft.com/library/aa369534)」に概説されているガイドラインに従う方法もあります  
  
## 参照  
 [配置例](../ide/deployment-examples.md)   
 [C\/C\+\+ 分離アプリケーションのビルド](../build/building-c-cpp-isolated-applications.md)   
 [C\/C\+\+ 分離アプリケーションおよび side\-by\-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)