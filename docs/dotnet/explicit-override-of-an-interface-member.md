---
title: "インターフェイス メンバーの明示的なオーバーライド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- virtual functions, explicit overrides
- overriding functions
- interface members, explicit overrides
- functions [C++], overriding
- explicit override of virtual function
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 85681b2e2aeeb6dbeb6ffdf511827fb1fc1cb029
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-override-of-an-interface-member"></a>インターフェイス メンバーの明示的なオーバーライド
クラス内で、インターフェイス メンバーの明示的なオーバーライドを宣言する構文は、Visual C を c++ マネージ拡張から変更されました。  
  
 多くの場合、インターフェイス ハンドル クラス オブジェクトを操作するときに使用されるいずれかと、クラス インターフェイスを通してクラス オブジェクトを使用する場合に使用される 1 つのインターフェイスを実装するクラス内で、インターフェイス メンバーの 2 つのインスタンスを提供します。 例:  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 マネージ拡張でこの作業を行う、インターフェイスの名前で修飾メソッドの名前を持つインターフェイス メソッドの明示的な宣言を提供することによりします。 クラスに固有のインスタンスは、修飾されていません。 戻り値をキャストする必要がある`Clone`のインスタンスを明示的に呼び出されたときに、この例では`R`します。  
  
 新しい構文では一般的なオーバーライドする機構が導入されました、マネージ拡張構文を置換します。 この例では、次のように書き換えることができます。  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 このリビジョンは、明示的にオーバーライドされているインターフェイスのメンバーである必要があります、クラス内で一意の名前を指定します。 ここでは、私の不適切な名前を指定している`InterfaceClone`です。 動作がも同じ - これまで、`ICloneable`インターフェイスを呼び出す、名前を変更`InterfaceClone`、型のオブジェクトからの呼び出し中に`R`もう 1 つを呼び出す`Clone`インスタンス。  
  
## <a name="see-also"></a>参照  
 [クラスまたはインターフェイス内でメンバーの宣言 (C + + CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [明示的なオーバーライド](../windows/explicit-overrides-cpp-component-extensions.md)