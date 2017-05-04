---
title: "Platform::WeakReference クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform::WeakReference"
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::WeakReference クラス
ref クラスのインスタンスへの弱い参照を表します。  
  
## 構文  
  
```vb  
class WeakReference  
```  
  
#### パラメーター  
  
## メンバー  
  
### コンストラクター  
  
|メンバー|説明|  
|----------|--------|  
|[WeakReference::WeakReference コンストラクター](../cppcx/weakreference-weakreference-constructor-c-cx.md)|WeakReference クラスの新しいインスタンスを初期化します。|  
  
### メソッド  
  
|メンバー|説明|  
|----------|--------|  
|[WeakReference::Resolve メソッド](../cppcx/weakreference-resolve-method-platform-namespace.md)|基になる ref クラスへのハンドル、またはオブジェクトが存在しない場合は nullptr を返します。|  
  
### 演算子  
  
|メンバー|説明|  
|----------|--------|  
|[WeakReference::operator\=](../cppcx/weakreference-operator-assign.md)|新しい値を WeakReference オブジェクトに代入します。|  
  
## 解説  
 WeakReference クラス自体は ref クラスではありません。したがって、WeakReference クラスは Platform::Object^ から継承せず、パブリック メソッドのシグネチャでは使用できません。  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)