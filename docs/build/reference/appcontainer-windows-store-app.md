---
title: "APPCONTAINER (Windows ストア アプリ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22ca7bec885f20518950626d33f7e3af553d0d52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="appcontainer-windows-store-app"></a>/APPCONTAINER (Windows ストア アプリ)
リンカーがアプリ コンテナーで実行される必要がある実行可能イメージを生成するかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 既定では、/APPCONTAINER は無効になっています。  
  
 このオプションは、実行可能ファイルを変更し、appcontainer プロセス分離環境でアプリが実行される必要があるかどうかを示します。 appcontainer 環境で実行される必要があるアプリに対し、/APPCONTAINER を指定します ([!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] アプリなど)  (テンプレートから [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] アプリを作成するときに、オプションは Visual Studio で自動的に設定されます)。デスクトップ アプリケーションでは、/APPCONTAINER:NO を指定するか、オプションを省略します。  
  
 /APPCONTAINER オプションは [!INCLUDE[win8](../../build/reference/includes/win8_md.md)] で導入されました。  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**コマンドライン**プロパティ ページ。  
  
5.  **追加オプション**、入力`/APPCONTAINER`または`/APPCONTAINER:NO`です。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)