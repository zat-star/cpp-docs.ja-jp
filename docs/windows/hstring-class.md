---
title: "HString クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString"
dev_langs: 
  - "C++"
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HSTRING ハンドルの操作をサポートします。  
  
## 構文  
  
```cpp  
class HString;  
```  
  
## 解説  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]では、HSTRING ハンドルを使用して文字列にアクセスすることができます。  HString クラスには、HSTRING ハンドルの使用を簡単にするための便利な関数と演算子が用意されています。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[HString::HString コンストラクター](../windows/hstring-hstring-constructor.md)|HString クラスの新しいインスタンスを初期化します。|  
|[HString::~HString デストラクター](../windows/hstring-tilde-hstring-destructor.md)|HString クラスの現在のインスタンスを破棄します。|  
  
### メンバー  
  
|名前|説明|  
|--------|--------|  
|[HString::Set メソッド](../Topic/HString::Set%20Method.md)|現在の HString オブジェクトの値を、指定したワイド文字列または HString パラメーターに設定します。|  
|[HString::Attach メソッド](../windows/hstring-attach-method.md)|指定した HString オブジェクトを現在の HString オブジェクトに関連付けます。|  
|[HString::CopyTo メソッド](../windows/hstring-copyto-method.md)|現在の HString オブジェクトを HSTRING オブジェクトにコピーします。|  
|[HString::Detach メソッド](../Topic/HString::Detach%20Method.md)|指定した HString オブジェクトと基になる値の関連付けを解除します。|  
|[HString::GetAddressOf メソッド](../windows/hstring-getaddressof-method.md)|基になる HSTRING ハンドルへのポインターを取得します。|  
|[HString::Get メソッド](../Topic/HString::Get%20Method.md)|基になる HSTRING ハンドルの値を取得します。|  
|[HString::Release メソッド](../windows/hstring-release-method.md)|基になる文字列値を削除し、現在の HString オブジェクトを空の値に初期化します。|  
|[HString::MakeReference メソッド](../Topic/HString::MakeReference%20Method.md)|指定した文字列パラメーターから HStringReference オブジェクトを作成します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[HString::Operator\= 演算子](../Topic/HString::Operator=%20Operator.md)|別の HString オブジェクトの値を現在の HString オブジェクトに移動します。|  
|[HString::Operator\=\= 演算子](../windows/hstring-operator-equality-operator.md)|2 つのパラメーターが等しいかどうかを示します。|  
|[HString::Operator\!\= 演算子](../windows/hstring-operator-inequality-operator.md)|2 つのパラメーターが異なるかどうかを示します。|  
  
## 継承階層  
 `HString`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [Microsoft::WRL::Wrappers 名前空間](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)