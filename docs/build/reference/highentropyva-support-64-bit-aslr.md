---
title: "-HIGHENTROPYVA (64 ビット ASLR のサポート) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 059f6169cafc48fc67587ae2f5827966269e6ac7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (64 ビット ASLR のサポート)
実行可能イメージが高いエントロピの 64 ビット ASLR (Address Space Layout Randomization) をサポートするように指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 既定では、/HIGHENTROPYVA は、64 ビットの実行可能イメージ上にあります。 32 ビットの実行可能イメージには適用されません。 このオプションを有効にするには、/DYNAMICBASE も有効にする必要があります。  
  
 /HIGHENTROPYVA は、64 ビット アドレスの ASLR がサポートされているかどうかを示す、.dll ファイルまたは .exe ファイルのヘッダーを変更します。 このオプションを実行可能ファイルおよび依存するモジュールのすべてに設定すると、64 ビット ASLR をサポートするオペレーティング システムは、読み込み時に 64 ビットの仮想アドレス空間でランダム化されたアドレスを使用して、実行可能イメージのセグメントのベース アドレスを再設定できます。 この大きいアドレス空間により、攻撃者は特定のメモリ領域の位置を推測することが困難となります。  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**コマンドライン**プロパティ ページ。  
  
5.  **追加オプション**、入力`/HIGHENTROPYVA`または`/HIGHENTROPYVA:NO`です。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)