---
title: "Platform::Agile クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile"
ms.assetid: e34459a9-c429-4c79-97fd-030c43ca4155
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Agile クラス
アジャイル オブジェクトとして MashalingBehavior\=Standard を含むオブジェクトを表します。これはランタイム スレッドの例外の頻度を大幅に減らします。`Agile<T>` を使うと、非アジャイル オブジェクトによる同じスレッドや別のスレッドの呼び出しや、同じスレッドや別のスレッドによる非アジャイル オブジェクトの呼び出しができるようになります。 詳細については、「[スレッドとマーシャリング](../cppcx/threading-and-marshaling-c-cx.md)」を参照してください。  
  
## 構文  
  
```scr  
  
template <typename T>  
    class Agile  
;  
```  
  
#### パラメーター  
 T  
 非アジャイル クラスの型名です。  
  
## 解説  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 内のクラスのほとんどはアジャイルです。 アジャイル オブジェクトは、同じスレッドまたは別のスレッドのインプロセスまたはアウトプロセス オブジェクトを呼び出すことができます。また、同じスレッドまたは別のスレッドのインプロセスまたはアウトプロセス オブジェクトから呼び出されることもできます。 オブジェクトがアジャイルでない場合、非アジャイル オブジェクトをアジャイルである `Agile<T>` オブジェクトにラップします。 その後、`Agile<T>` オブジェクトをマーシャリングしたり、基になる非アジャイル オブジェクトを使ったりできるようになります。  
  
 `Agile<T>` クラスはネイティブな標準 C\+\+ クラスであり、`agile.h` が必要です。 これは、非アジャイル オブジェクトと、Agile オブジェクトの*コンテキスト*を表します。 コンテキストは、アジャイル オブジェクトのスレッド モデルとマーシャリング動作を指定します。 オペレーティング システムは、コンテキストを使って、オブジェクトをマーシャリングする方法を決定します。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Agile::Agile コンストラクター](../cppcx/agile-agile-constructor.md)|アジャイル クラスの新しいインスタンスを初期化します。|  
|[Agile::~Agile デストラクター](../cppcx/agile-tilde-agile-destructor.md)|Agile クラスの現在のインスタンスを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[Agile::Get](../cppcx/agile-get-method.md)|現在の Agile オブジェクトによって表されるオブジェクトへのハンドルを返します。|  
|[Agile::GetAddressOf](../cppcx/agile-getaddressof-method.md)|現在の Agile オブジェクトを再初期化し、`T` 型のオブジェクトへのハンドルのアドレスを返します。|  
|[Agile::GetAddressOfForInOut](../cppcx/agile-getaddressofforinout-method.md)|現在の Agile オブジェクトによって表されるオブジェクトへのハンドルのアドレスを返します。|  
|[Agile::Release](../cppcx/agile-release-method.md)|現在の Agile オブジェクトの基になるオブジェクトとコンテキストを破棄します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[Agile::operator\-\>](../cppcx/agile-operator-arrow-operator.md)|現在の Agile オブジェクトによって表されるオブジェクトへのハンドルを取得します。|  
|[Agile::operator\=](../cppcx/agile-operator-assign-operator.md)|指定された値を現在の Agile オブジェクトに割り当てます。|  
  
## 継承階層  
 `Object`  
  
 `Agile`  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** agile.h  
  
## 参照  
 [\(NOTINBUILD\) Platform 名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)