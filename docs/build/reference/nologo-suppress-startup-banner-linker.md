---
title: "-NOLOGO (著作権情報を抑制する) (リンカー) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
dev_langs: C++
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c9cffaea51ad1ba17462292f4feae531361200d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (著作権情報の非表示) (リンカー)
```  
/NOLOGO  
```  
  
## <a name="remarks"></a>コメント  
 /NOLOGO オプションでは、著作権メッセージとバージョン番号が表示されなくなります。  
  
 このオプションでは、コマンド ファイルのエコーも行われません。 詳細については、「 [LINK コマンド ファイル](../../build/reference/link-command-files.md)です。  
  
 既定では、この情報は、出力ウィンドウをリンカーに送信します。 コマンド ラインでは、標準出力に送信され、ファイルにリダイレクトできます。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  このオプションは、コマンドラインからのみ使用する必要があります。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  このリンカー オプションをプログラムで変更できません。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)