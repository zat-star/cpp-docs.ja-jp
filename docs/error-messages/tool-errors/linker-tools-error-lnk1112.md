---
title: "リンカ ツール エラー LNK1112 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1112
dev_langs: C++
helpviewer_keywords: LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a915768f0668a4ce276962f9eafd1f905980e2be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1112"></a>リンカ ツール エラー LNK1112
モジュールのコンピューターの種類 'type1' は対象コンピューターの種類 'type2' と競合しています。  
  
 入力として指定されたオブジェクト ファイルは、別のコンピューターの種類用にコンパイルされています。  
  
 たとえば、 **/clr** でコンパイルされたオブジェクト ファイルを、 **/clr:pure** (コンピューターの種類 CEE) でコンパイルされたオブジェクト ファイルとリンクしようとした場合、リンカーはエラー LNK1112 を生成します。  
  
 同様に、 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] コンパイラを使用して 1 つのモジュールを作成し、x86 コンパイラを使用して別のモジュールを作成して、それらをリンクしようとすると、リンカーが LNK1112 を生成します。  
  
 このエラーの原因としては、64 ビット アプリケーションを開発しているのに、Visual C++ の 64 ビット コンパイラをインストールしていない可能性があります。 この場合は、64 ビットの構成は使用できません。 この問題を修正するには、Visual Studio のインストーラーを実行し、不足している C++ コンポーネントをインストールします。  
  
 このエラーは、 **構成マネージャー** の **アクティブ ソリューション構成** を変更する場合にも発生する可能性があり、その場合は中間出力ファイルを削除する前にプロジェクトのビルドを試行します。 このエラーを解決するには、 **[ビルド]** メニューから **[ソリューションのリビルド]** を選択します。 **[ビルド]** メニューから **[ソリューションのクリーン]** を選択して、ソリューションをビルドすることもできます。  
  
## <a name="see-also"></a>参照  
 [リンカー ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)