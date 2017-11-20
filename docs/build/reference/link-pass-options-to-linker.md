---
title: "-リンク (リンカーにオプションを渡します) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /link
dev_langs: C++
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e2a193ff5f1e76d4e7ceb160325c1e748634c3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="link-pass-options-to-linker"></a>/link (リンカーにオプションを渡す)
1 つまたは複数のリンカー オプションをリンカーに渡します。  
  
## <a name="syntax"></a>構文  
  
```  
/link linkeroptions  
```  
  
## <a name="arguments"></a>引数  
 `linkeroptions`  
 リンカー オプションまたはリンカーに渡されるオプションです。  
  
## <a name="remarks"></a>コメント  
 **/Link**オプションとそのリンカー オプションは、ファイル名と CL オプションの後に表示する必要があります。 スペースは間で必要な**/link**と`linkeroptions`です。 詳細については、次を参照してください。[リンカー オプションの設定](../../build/reference/setting-linker-options.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  リンカー プロパティ ページをクリックします。  
  
4.  1 つまたは複数のプロパティを変更します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   このコンパイラ オプションをプログラムで変更できません。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)