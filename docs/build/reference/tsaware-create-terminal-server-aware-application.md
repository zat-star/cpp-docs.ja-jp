---
title: "/TSAWARE (ターミナル サーバーに対応したアプリケーションの作成) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/tsaware"
  - "VC.Project.VCLinkerTool.TerminalServerAware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TSAWARE リンカー オプション"
  - "ターミナル サーバー"
  - "ターミナル サーバー, ターミナル サーバーに対応したアプリケーション"
  - "TSAWARE リンカー オプション"
  - "-TSAWARE リンカー オプション"
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /TSAWARE (ターミナル サーバーに対応したアプリケーションの作成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TSAWARE[:NO]  
```  
  
## 解説  
 \/TSAWARE オプションは、プログラム イメージのオプションのヘッダーにある IMAGE\_OPTIONAL\_HEADER DllCharacteristics フィールドにフラグを設定します。  このフラグが設定されていると、ターミナル サーバーはアプリケーションに対して特定の変更を加えません。  
  
 アプリケーションがターミナル サーバーに対応していない場合 \(従来のアプリケーション\)、マルチユーザー環境で正しく動作するようにアプリケーションに対して特定の変更が加えられます。  たとえば、仮想 Windows フォルダーを作成して、ユーザーがシステムの Windows ディレクトリではなく、Windows フォルダーを使用できるようにします。  これにより、ユーザーはそれぞれの INI ファイルにアクセスできます。  また、ターミナル サーバーは従来のアプリケーションのレジストリを調整します。  この変更を加えると、従来のアプリケーションをターミナル サーバーに読み込むときに時間がかかります。  
  
 ターミナル サーバーに対応したアプリケーションは、INI ファイルに依存したり、セットアップ時に **HKEY\_CURRENT\_USER** レジストリに書き込んだりする必要はありません。  
  
 \/TSAWARE を使用した場合、アプリケーションで INI ファイルを使用し続けると、INI ファイルはシステムのすべてのユーザー間で共有されます。  ファイルの共有を受け入れる場合は、\/TSAWARE を使用してアプリケーションをリンクします。それ以外の場合は、\/TSAWARE:NO を使用する必要があります。  
  
 Windows アプリケーションおよびコンソール アプリケーションを使用する場合、\/TSAWARE オプションは Windows 2000 以降では既定で有効に設定されます。  詳細については、「[\/SUBSYSTEM \(サブシステムの指定\)](../../build/reference/subsystem-specify-subsystem.md)」および「[\/VERSION \(バージョン情報\)](../Topic/-VERSION%20\(Version%20Information\).md)」を参照してください。  
  
 \/TSAWARE は、VxDs や DLL などのドライバーには使用できません。  
  
 \/TSAWARE オプションを使用してリンクされたアプリケーションの場合は、DUMPBIN [\/HEADERS](../../build/reference/headers.md) によってその情報が表示されます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[システム\] プロパティ ページをクリックします。  
  
4.  \[ターミナル サ\-バー\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [Storing User\-Specific Information](http://msdn.microsoft.com/library/aa383452)   
 [Legacy Applications in a Terminal Services Environment](https://msdn.microsoft.com/en-us/library/aa382957.aspx)