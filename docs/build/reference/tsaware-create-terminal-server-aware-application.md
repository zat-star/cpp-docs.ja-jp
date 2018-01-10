---
title: "-TSAWARE (ターミナル サーバーの対応するアプリケーションの作成) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
dev_langs: C++
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c6fb783f717f730945f8d34c8fe2a03f5e1f6d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (ターミナル サーバーに対応したアプリケーションの作成)
```  
/TSAWARE[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 /TSAWARE オプションは、プログラム イメージの省略可能なヘッダーに IMAGE_OPTIONAL_HEADER DllCharacteristics フィールドにフラグを設定します。 このフラグが設定されると、ターミナル サーバーはアプリケーションに特定の変更を加えなくなります。  
  
 アプリケーションがターミナル サーバーに注意してください (レガシ アプリケーションとも呼ばれます) ではないときに、ターミナル サーバーはマルチ ユーザー環境で正しく動作させるために、レガシ アプリケーションに対して特定の変更がします。 たとえば、ターミナル サーバーであっても、各ユーザーが、システムの Windows ディレクトリを取得する代わりに Windows フォルダーを取得するよう、仮想 Windows フォルダーが作成されます。 これにより、ユーザーは自分の INI ファイルにアクセスできるようにします。 さらに、ターミナル サーバーは、レガシ アプリケーションのレジストリにいくつかの調整がします。 これらの変更には、ターミナル サーバー上のレガシ アプリケーションの読み込みが低速です。  
  
 アプリケーションがない場合はターミナル サーバーに対応した、その必要がありますも INI ファイルに依存してへの書き込み、 **HKEY_CURRENT_USER**セットアップ中にレジストリです。  
  
 /TSAWARE を使用すると、アプリケーションが現在も INI ファイルを使用して、ファイルは、システムのすべてのユーザーによって共有されます。 許容可能な場合は、/TSAWARE; を使用してアプリケーションをまだリンクすることができます。それ以外の場合は、/TSAWARE:NO を使用する必要があります。  
  
 /TSAWARE オプションは、Windows およびコンソール アプリケーションの Windows 2000 以降の既定で有効です。 参照してください[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)と[/VERSION](../../build/reference/version-version-information.md)についてです。  
  
 ドライバー、Vxd、Dll に関する/TSAWARE が正しくありません。  
  
 アプリケーションが/TSAWARE、DUMPBIN にリンクされているかどうかは[/HEADERS](../../build/reference/headers.md)それを情報が表示されます。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**システム**プロパティ ページ。  
  
4.  変更、**ターミナル サーバー**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [ユーザーに固有の情報を格納します。](http://msdn.microsoft.com/library/aa383452)   
 [ターミナル サービス環境でのレガシ アプリケーション](https://msdn.microsoft.com/en-us/library/aa382957.aspx)