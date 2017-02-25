---
title: "enable_shared_from_this クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1.enable_shared_from_this"
  - "enable_shared_from_this"
  - "std.tr1.enable_shared_from_this"
  - "memory/std::tr1::enable_shared_from_this"
  - "std::tr1::enable_shared_from_this"
  - "tr1::enable_shared_from_this"
  - "std.enable_shared_from_this"
  - "memory/std::enable_shared_from_this"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "enable_shared_from_this クラス"
  - "enable_shared_from_this クラス [TR1]"
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# enable_shared_from_this クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`shared_ptr` の生成を支援します。  
  
## 構文  
  
```  
template<class Ty>  
    class enable_shared_from_this {  
public:  
    shared_ptr<Ty> shared_from_this();  
    shared_ptr<const Ty> shared_from_this() const;  
  
protected:  
    enable_shared_from_this();  
    enable_shared_from_this(const enable_shared_from_this&);  
    enable_shared_from_this& operator=(const enable_shared_from_this&);  
    ~enable_shared_from_this();  
    };  
```  
  
#### パラメーター  
 `Ty`  
 共有ポインターによって制御される型。  
  
## 解説  
 派生したオブジェクト `enable_shared_from_this` 使える、 `shared_from_this` メソッドを作成するメンバー関数で [shared\_ptr](../standard-library/shared-ptr-class.md) 既存の所有権を共有するインスタンスの所有者 `shared_ptr` 所有者。 それ以外の場合、新規に作成する場合は、 `shared_ptr` を使用して `this`, は既存の別 `shared_ptr` 所有者は、参照が無効です。 または、複数回削除するオブジェクトが発生する基になることができます。  
  
 偶発的な誤用を防ぐためには、コンス トラクター、デストラクター、および代入演算子が保護されます。 テンプレート引数の型 `Ty` 派生クラスの型にする必要があります。  
  
 使用状況の例は、次を参照してください。 [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md)します。  
  
## 必要条件  
 **ヘッダー:** \<memory\>  
  
 **名前空間:** std  
  
## 参照  
 [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md)   
 [shared\_ptr クラス](../standard-library/shared-ptr-class.md)