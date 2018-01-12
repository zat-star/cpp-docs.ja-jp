---
title: "-DELAYLOAD (遅延読み込みのインポート) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
dev_langs: C++
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fd524e72125408c6a88bea83272e18a7ef9b78d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (遅延読み込みのインポート)
```  
/DELAYLOAD:dllname  
```  
  
## <a name="parameters"></a>パラメーター  
 `dllname`  
 遅延読み込みする DLL の名前。  
  
## <a name="remarks"></a>コメント  
 /DELAYLOAD オプションを指定すると、`dllname` で指定された DLL は、その DLL 内の関数に対するプログラムの最初の呼び出しが行われたときのみ読み込まれます。 詳細については、次を参照してください。[リンカーによる dll の Delay-Loaded](../../build/reference/linker-support-for-delay-loaded-dlls.md)です。 このオプションは、選択した DLL を指定するのに必要なだけ繰り返して使用できます。 プログラムを Delayimp.lib にリンクする場合は、Delayimp.lib を使用する必要があります。または、独自の遅延読み込みヘルパー関数を実装することもできます。  
  
 [/Delay](../../build/reference/delay-delay-load-import-settings.md)オプションのバインドと読み込みの遅延読み込みされる各 DLL のオプションを指定します。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **リンカー**フォルダーを選択、**入力**プロパティ ページ。  
  
3.  変更、 **Dll の遅延読み込み**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)