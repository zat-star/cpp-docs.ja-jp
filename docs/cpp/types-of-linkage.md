---
title: リンケージの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
- linkage [C++], types of
- types [C++], linkage
- internal linkage, types of linkage
- external linkage, linkage types
ms.assetid: 41326c7f-4602-4bad-a648-697604858ba0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfddf0105603311179340a0c6b0b2e8fb328b134
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="types-of-linkage"></a>リンケージの種類
オブジェクトと関数の名前が翻訳単位間でどのように共有されるかを、リンケージと呼びます。 これらの名前が持つ可能性のあるリンケージは、次のとおりです。  
  
-   内部リンケージ。この場合、各名前は自分の翻訳単位内のプログラム要素しか参照しません。名前は他の翻訳単位と共有されません。  
  
     別の翻訳単位に存在する同じ名前は、異なるオブジェクトまたは異なるクラスを参照する場合があります。 内部リンケージを持つ名前は、翻訳単位に対してローカルとも呼ばれます。  
  
     内部リンケージを持つ名前の宣言の例は次のとおりです。  
  
    ```  
    static int i;   // The static keyword ensures internal linkage.  
    ```  
  
-   外部リンケージ。この場合、各名前はプログラム内のすべての翻訳単位のプログラム要素を参照できます。プログラム要素は翻訳単位間で共有されます。  
  
     別の翻訳単位に存在する同じ名前は、必ず同じオブジェクトまたはクラスを参照します。 外部リンケージを持つ名前は、グローバルとも呼ばれます。  
  
     外部リンケージを持つ名前の宣言の例は次のとおりです。  
  
    ```  
    extern int i;  
    ```  
  
-   リンケージなし。この場合、各名前は一意のエンティティを参照します。 別のスコープの同じ名前が、同じオブジェクトを参照していないことがあります。 列挙はその一例です (ただし、リンケージを持たないオブジェクトへのポインターを渡すことができます。 これにより、他の翻訳単位内のオブジェクトにアクセスできます)。  
  
## <a name="see-also"></a>関連項目  
 [プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)