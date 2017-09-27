---
title: "追加の起動に関する考慮事項 |Microsoft ドキュメント"
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
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
caps.latest.revision: 6
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
ms.openlocfilehash: cb437729d2c60f15bc798438ecbbba0637bf3d22
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="additional-startup-considerations"></a>起動に関するその他の考慮事項
C++ では、オブジェクトの構築時と破棄時にユーザー コードを実行することができます。 したがって、どの初期化に入る前に発生する可能性を理解しておく必要は**メイン**から出た後にどのデストラクターが呼び出されると**メイン**です。 (オブジェクトの構築と破棄の詳細については、次を参照してください[コンス トラクター](../cpp/constructors-cpp.md)と[デストラクター](../cpp/destructors-cpp.md)。)。  
  
 入る前に次の初期化が行わ**メイン**:  
  
-   静的データのゼロへの既定の初期化。 明示的な初期化子のないすべての静的データは、ランタイム初期化も含めて、他のコードを実行する前にゼロに設定されます。 その場合でも、静的データ メンバーは明示的に定義する必要があります。  
  
-   翻訳単位でのグローバルな静的オブジェクトの初期化。 これは、エラーは発生に入る前にいずれかの**メイン**または任意の関数またはオブジェクトの翻訳単位内のオブジェクトの最初に使用する前にします。  
  
 **Microsoft 固有の仕様**  
  
 Microsoft C では、グローバルな静的オブジェクトに入る前に初期化されます**メイン**です。  
  
 **Microsoft 固有の仕様はここまで**  
  
 相互依存しているのに翻訳単位が異なるグローバルな静的オブジェクトは、正しくない動作の原因になる可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [起動と終了](../cpp/startup-and-termination-cpp.md)
