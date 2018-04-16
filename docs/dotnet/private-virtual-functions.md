---
title: "プライベート仮想関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, private
- derived classes, virtual functions
- access modifiers [C++], for class members
- member access [C++], virtual members
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b407bc469a345706f99cf5bad578f678e652a4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="private-virtual-functions"></a>プライベート仮想関数
派生クラスでプライベート仮想関数の処理方法は、Visual C を c++ マネージ拡張から変更されました。  
  
 マネージ拡張で、仮想関数のアクセス レベルは、派生クラス内でオーバーライドされるように機能を制限しません。 新しい構文では、仮想関数はアクセスできない基底クラスの仮想関数をオーバーライドできません。 例:  
  
```  
__gc class MyBaseClass {  
   // inaccessible to a derived class   
   virtual void g();  
};  
  
__gc class MyDerivedClass : public MyBaseClass {  
public:  
   // okay in Managed Extensions; g() overrides MyBaseClass::g()  
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible  
   void g();  
};  
```  
  
 このような新しい構文にデザインの実際のマッピングはありません。 1 つは、基本クラスのメンバー アクセスできるようにするには、非プライベート単にあります。 継承されたメソッドは、同じアクセス許可に注意する必要はありません。 この例では、影響を最小限の変更が MyBaseClass メンバーにするのには`protected`します。 このように MyBaseClass を通じてメソッドへの一般的なプログラムのアクセスはまだ禁止されています。  
  
```  
ref class MyBaseClass {  
protected:  
   virtual void g();  
};  
  
ref class MyDerivedClass : MyBaseClass {  
public:  
   virtual void g() override;  
};  
```  
  
 なおがない場合、明示的な`virtual`新しい構文では、基本クラスのキーワードは、警告メッセージを生成します。  
  
## <a name="see-also"></a>参照  
 [クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 