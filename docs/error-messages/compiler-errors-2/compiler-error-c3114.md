---
title: "コンパイラ エラー C3114 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3114
dev_langs:
- C++
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 509c0dd1d85187871e78cfa93a66bc4ef385bbb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3114"></a>コンパイラ エラー C3114
'argument': 名前付き属性引数を有効ではありません  
  
 属性クラスのデータ メンバーを引数の名前が有効にするためには、そのマークしないでください`static`、 `const`、または`literal`です。 プロパティの有効期限がありますいない場合、プロパティを`static`とする必要があります get および set アクセサー。  
  
 詳細については、次を参照してください。[プロパティ](../../windows/property-cpp-component-extensions.md)と[ユーザー定義の属性](../../windows/user-defined-attributes-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3114 を生成します。  
  
```  
// C3114.cpp  
// compile with: /clr /c  
public ref class A : System::Attribute {  
public:  
   static property int StaticProp {  
      int get();  
   }  
  
   property int Prop2 {  
      int get();  
      void set(int i);  
   }  
};  
  
[A(StaticProp=123)]   // C3114  
public ref class R {};  
  
[A(Prop2=123)]   // OK  
public ref class S {};  
```