---
title: "遅延 (遅延読み込みのインポート設定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
dev_langs: C++
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 86b076b8a3591ef75ad07cd47a525e67576317f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (遅延読み込みのインポート設定)
```  
/DELAY:UNLOAD  
/DELAY:NOBIND  
```  
  
## <a name="remarks"></a>コメント  
 /DELAY オプション コントロール[遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)(dll を)。  
  
-   UNLOAD 修飾子は、DLL の明示的なアンロードをサポートするように遅延読み込みヘルパー関数に指定します。 インポート アドレス テーブル (IAT) は元の形式にリセットされ、IAT のポインターは無効になって上書きされます。  
  
     すべての呼び出しにアンロードを選択しない場合[FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)は失敗します。  
  
-   NOBIND 修飾子は、バインドできる IAT を最終イメージに含めないようにリンカーに指定します。 既定では、遅延読み込みされる DLL に対してバインドできる IAT が作成されます。 生成されるイメージは静的にバインドできません。 (バインドできる IAT を含むイメージは、実行前に静的にバインドできます)。参照してください[/bind](../../build/reference/bind.md)です。  
  
     ヘルパー関数が呼び出す代わりに、バインドされた情報を使用しようとして、DLL がバインドされている場合[GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)参照されているインポートごとにします。 タイムスタンプまたは優先アドレスが、読み込まれた DLL のものと一致しない場合、ヘルパー関数はバインドされた IAT は古いと見なし、バインドされた IAT が存在しないかのように続行します。  
  
     NOBIND を使用すると、プログラム イメージは大きくなりますが、DLL の読み込み時間は速くなります。 DLL をバインドしない場合は、NOBIND を使用すると、バインドされた IAT は生成されません。  
  
 遅延読み込みする Dll を指定するには、使用、 [/DELAYLOAD](../../build/reference/delayload-delay-load-import.md)オプション。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開**構成プロパティ**、**リンカー**、し、**詳細**です。  
  
3.  変更、 **DLL の遅延読み込み**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)