---
title: "Object::GetHashCode メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetHashCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform、Object::GetHashCode"
ms.assetid: 403a60e9-be1d-4702-b14d-27fa4b2a043b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::GetHashCode メソッド
COM オブジェクトの場合は、このインスタンスの [IUnknown](../atl/iunknown.md)\* ID 値を返します。COM オブジェクトでない場合は、計算済みハッシュ値を返します。  
  
## 構文  
  
```cpp  
public:int GetHashCode()  
```  
  
## 戻り値  
 このオブジェクトを一意に識別する数値。  
  
## 解説  
 GetHashCode を使用してマップ内のオブジェクトのキーを作成できます。[Object::Equals メソッド](../cppcx/object-equals-method.md) を使用することで、ハッシュ コードを比較できます。 コード パスが非常に重要であるときに、`GetHashCode` と `Equals` の実行速度が不十分な場合には、基になる COM レイヤーまで移動して [IUnknown](../atl/iunknown.md) ネイティブ ポインターの比較を実行できます。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Object クラス](../cppcx/platform-object-class.md)