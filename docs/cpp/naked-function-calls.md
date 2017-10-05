---
title: "Naked 関数の呼び出し |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- virtual device drivers
- VXD virtual device drivers
- virtual device drivers, naked function calls
- naked functions
- prolog code
- epilog code
- naked keyword [C++]
- naked keyword [C++], storage-class attribute
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: dcf93756bf4d10feb63238a1ecf3b6d3f8b340f6
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="naked-function-calls"></a>naked 関数呼び出し
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 宣言された関数、`naked`を使用して、独自のカスタム プロローグとエピローグ シーケンスを記述できるように、プロローグまたはエピローグのコードがない属性が出力されます、[インライン アセンブラー](../assembler/inline/inline-assembler.md)です。 naked 関数は高度な機能です。 これにより、C/C++ 以外のコンテキストから呼び出される関数を宣言して、パラメーターの存在する場所や保持されるレジスタについて、異なる想定をすることができます。 例としては、割り込みハンドラーのようなルーチンが挙げられます。 この機能は、仮想デバイス ドライバー (VxD) を作成するときに特に便利です。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [naked 関数に関する規則と制限](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [プロローグ/エピローグ コードの記述に関する考慮事項](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規約](../cpp/calling-conventions.md)
