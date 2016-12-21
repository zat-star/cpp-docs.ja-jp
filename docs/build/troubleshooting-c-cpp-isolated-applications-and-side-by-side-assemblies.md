---
title: "C/C++ 分離アプリケーションおよび side-by-side アセンブリのトラブルシューティング | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "トラブルシューティング (分離アプリケーション)"
  - "トラブルシューティング (side-by-side アセンブリ)"
  - "トラブルシューティング (Visual C++)"
ms.assetid: 3257257a-1f0b-4ede-8564-9277a7113a35
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 分離アプリケーションおよび side-by-side アセンブリのトラブルシューティング
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

依存するライブラリが見つからない場合は、C\/C\+\+ アプリケーションの読み込みに失敗する場合があります。  ここでは、C\/C\+\+ アプリケーションの読み込みに失敗するいくつかの一般的な理由について説明し、問題を解決する手順を提示します。  
  
 side\-by\-side アセンブリに対する依存関係を指定するマニフェストがアプリケーションに含まれていて、そのアセンブリが実行可能ファイルと同じフォルダーにも %WINDIR%\\WinSxS\\ フォルダーのネイティブ アセンブリ キャッシュにもプライベート アセンブリとしてインストールされていないことが原因でアプリケーションが読み込みに失敗した場合、アプリケーションを実行しようとしている Windows のバージョンに応じて、次のいずれかのエラー メッセージが表示されることがあります。  
  
-   アプリケーションを正しく初期化できませんでした \(0xc0000135\)。  
  
-   アプリケーション構成が正しくないため、このアプリケーションの開始に失敗しました。  アプリケーションを再度インストールすることにより問題が解決する場合があります。  
  
-   指定されたプログラムを実行できません。  
  
 アプリケーションにマニフェストが含まれておらず、Windows が一般的な検索場所で見つけることができない DLL にアプリケーションが依存している場合、次のようなエラー メッセージが表示されることがあります。  
  
-   *必要な DLL* が見つからなかったため、このアプリケーションを開始できませんでした。  アプリケーションをインストールし直すとこの問題は解決される場合があります。  
  
 Visual Studio がインストールされていないコンピューターにアプリケーションが配置されていて、上記と似たエラー メッセージでアプリケーションがクラッシュした場合は、次の点を確認してください。  
  
1.  「[Visual C\+\+ アプリケーションの依存関係の理解](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)」に説明されている手順に従います。  Dependency Walker では、アプリケーションまたは DLL のほとんどの依存関係を表示できます。  表示されていない DLL がある場合は、アプリケーションを実行するコンピューターにその DLL をインストールしてください。  
  
2.  オペレーティング システム ローダーは、アプリケーション マニフェストを使用してアプリケーションが依存するアセンブリを読み込みます。  マニフェストは、リソースとしてバイナリに埋め込むことも、個別のファイルとしてアプリケーション フォルダーにインストールすることもできます。  マニフェストがバイナリ内に埋め込まれているかどうかを確認するには、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] でバイナリを開き、リソースの一覧で RT\_MANIFEST を探します。  埋め込まれたマニフェストが見つからない場合は、アプリケーション フォルダーで \<binary\_name\>.\<extension\>.manifest のような名前のファイルを探します。  
  
3.  アプリケーションが side\-by\-side アセンブリに依存していて、マニフェストが存在しない場合は、リンカーにプロジェクトのマニフェストを生成させる必要があります。  プロジェクトの **\[プロジェクトのプロパティ\]** ダイアログ ボックスの **\[マニフェストの生成\]** リンカー オプションをオンにします。  
  
4.  マニフェストがライブラリ内に埋め込まれている場合は、RT\_MANIFEST の ID がこのタイプのバイナリに適した ID であることを確認します。  使用するリソース ID の詳細については、「[side\-by\-side アセンブリをリソースとして使用する \(Windows\)](http://msdn.microsoft.com/library/windows/desktop/aa376617.aspx)」を参照してください。  マニフェストが個別ファイルの場合は、XML エディターまたはテキスト エディターで開きます。  マニフェストおよび配置のルールの詳細については、「[Manifests \(マニフェスト\)](http://msdn.microsoft.com/library/aa375365)」を参照してください。  
  
    > [!NOTE]
    >  埋め込みマニフェストと個別マニフェスト ファイルの両方が存在する場合、オペレーティング システム ローダーは埋め込みマニフェストを使用し、個別ファイルは無視します。  ただし、Windows XP ではその反対です。つまり、個別マニフェスト ファイルが使用され、埋め込みマニフェストは無視されます。  
  
5.  DLL が `LoadLibrary` 呼び出しによって読み込まれるときには外部マニフェストは無視されるため、すべての DLL にマニフェストを埋め込むことをお勧めします。  詳細については、「[アセンブリ マニフェスト](http://msdn.microsoft.com/library/aa374219)」を参照してください。  
  
6.  マニフェストに列挙されているすべてのアセンブリがコンピューターに正しくインストールされていることを確認します。  各アセンブリは、名前、バージョン番号、およびプロセッサ アーキテクチャでマニフェストに指定されます。  アプリケーションが side\-by\-side アセンブリに依存している場合は、これらのアセンブリがコンピューターに適切にインストールされ、オペレーティング システム ローダーで検出できることを、「[Assembly Searching Sequence \(アセンブリの検索手順\)](http://msdn.microsoft.com/library/aa374224)」の説明に従って確認します。  64 ビット アセンブリは、32 ビット プロセスで読み込んだり、32 ビット オペレーティング システムで実行したりできないことに注意してください。  
  
## 例  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] でビルドされた appl.exe というアプリケーションがあるとします。  アプリケーション マニフェストは、ID が 1 のバイナリ リソース RT\_MANIFEST として appl.exe 内に埋め込まれているか、個別ファイル appl.exe.manifest として格納されています。  このマニフェストの内容は次のようになります。  
  
```  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <dependency>  
    <dependentAssembly>  
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>  
    </dependentAssembly>  
  </dependency>  
</assembly>  
```  
  
 このマニフェストは、オペレーティング システム ローダーに対して、appl.exe が、32 ビットの x86 プロセッサ アーキテクチャ用にビルドされた Fabrikam.SxS.Library という名前のバージョン 2.0.20121.0 のアセンブリに依存していることを通知します。  依存 side\-by\-side アセンブリは、共有アセンブリまたはプライベート アセンブリとしてインストールできます。  
  
 共有アセンブリのアセンブリ マニフェストは、%WINDIR%\\WinSxS\\Manifests\\ フォルダーにインストールされます。  また、アセンブリを識別して、その内容 \(アセンブリに含まれる DLL\) を一覧表示します。  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
   <noInheritable/>  
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>  
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>  
</assembly>  
```  
  
 side\-by\-side アセンブリは、ポリシー ファイルとも呼ばれる[発行者構成ファイル](http://msdn.microsoft.com/library/aa375682)を使用して、アプリケーションおよびアセンブリがあるバージョンの side\-by\-side アセンブリを別のバージョンの side\-by\-side アセンブリの代わりに使用するようにグローバルにリダイレクトすることもできます。  共有アセンブリのポリシーは、%WINDIR%\\WinSxS\\Policies\\ フォルダーで確認できます。  ポリシー ファイルの例を次に示します。  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  
   <assemblyIdentity type="win32-policy" name="policy.2.0.Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <dependency>  
      <dependentAssembly>  
         <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
         <bindingRedirect oldVersion="2.0.10000.0-2.0.20120.99" newVersion="2.0.20121.0"/>  
      </dependentAssembly>  
   </dependency>  
</assembly>  
```  
  
 このポリシー ファイルは、アプリケーションまたはアセンブリが、このアセンブリのバージョン 2.0.10000.0 を要求する場合は、代わりにシステムに現在インストールされているバージョン 2.0.20121.0 を使用するように指定しています。  アプリケーションのマニフェストで示されたアセンブリのバージョンがポリシー ファイルに指定されている場合、ローダーは、マニフェストで指定されたバージョンのアセンブリを、%WINDIR%\\WinSxS\\ フォルダーで探します。このバージョンがインストールされていない場合、読み込みは失敗します。  バージョン 2.0.20121.0 のアセンブリがインストールされていない場合、バージョン 2.0.10000.0 のアセンブリを要求するアプリケーションで読み込みが失敗します。  
  
 ただし、アセンブリは、インストールされたアプリケーションのフォルダーにプライベート side\-by\-side アセンブリとしてインストールされている可能性もあります。  オペレーティング システムは、共有アセンブリとしてのアセンブリの検出に失敗した場合、そのアセンブリをプライベート アセンブリとして次の順序で検索します。  
  
1.  アプリケーション フォルダーで \<assemblyName\>.manifest という名前のマニフェスト ファイルを検索します。  この例では、ローダーは、appl.exe が格納されているフォルダーで Fabrikam.SxS.Library.manifest を検索します。  マニフェストが見つかった場合、ローダーはアプリケーション フォルダーからアセンブリを読み込みます。  アセンブリが見つからない場合、読み込みは失敗します。  
  
2.  appl.exe が格納されているフォルダーで \\\<assemblyName\>\\ フォルダーを開こうとし、\\\<assemblyName\>\\ が存在する場合は、このフォルダーから \<assemblyName\>.manifest という名前のマニフェストを読み込もうとします。  マニフェストが見つからない場合、ローダーは \\\<assemblyName\>\\ フォルダーからアセンブリを読み込みます。  アセンブリが見つからない場合、読み込みは失敗します。  
  
 ローダーで依存アセンブリを検索する方法の詳細については、「[Assembly Searching Sequence \(アセンブリの検索手順\)](http://msdn.microsoft.com/library/aa374224)」を参照してください。  ローダーがプライベート アセンブリとしての依存アセンブリの検出に失敗した場合、読み込みは失敗し、"指定されたプログラムを実行できません。" というメッセージが表示されます。  このエラーを解決するには、依存アセンブリとそれを構成する DLL をプライベート アセンブリまたは共有アセンブリとしてコンピューターにインストールする必要があります。  
  
## 参照  
 [分離アプリケーションおよび side\-by\-side アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C\/C\+\+ 分離アプリケーションおよび side\-by\-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)