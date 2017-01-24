---
title: "CAdapt クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAdapt"
  - "ATL.CAdapt<T>"
  - "ATL::CAdapt"
  - "ATL::CAdapt<T>"
  - "CAdapt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& 演算子, address-of 演算子"
  - "アダプター オブジェクト"
  - "address-of 演算子"
  - "CAdapt クラス"
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAdapt クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このテンプレートは、オブジェクトのアドレス以外の値を返すために、アドレス演算子を再定義するクラスをラップするときに使用されます。  
  
## 構文  
  
```  
  
      template <  
   class T  
>  
class CAdapt  
```  
  
#### パラメーター  
 `T`  
 適合された型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAdapt::CAdapt](../Topic/CAdapt::CAdapt.md)|コンストラクターです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAdapt::operator const T&](../Topic/CAdapt::operator%20const%20T&.md)|`m_T` への `const` 参照を返します。|  
|[CAdapt::operator T&](../Topic/CAdapt::operator%20T&.md)|`m_T` への参照を返します。|  
|[CAdapt::operator \<](../Topic/CAdapt::operator%20%3C.md)|適合された型のオブジェクトを `m_T` と比較します。|  
|[CAdapt::operator \=](../Topic/CAdapt::operator%20=.md)|適合された型のオブジェクトを `m_T` に割り当てます。|  
|[CAdapt::operator \=\=](../Topic/CAdapt::operator%20==.md)|適合された型のオブジェクトを `m_T` と比較します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAdapt::m\_T](../Topic/CAdapt::m_T.md)|適合しているデータ。|  
  
## 解説  
 `CAdapt` は、オブジェクトのアドレス以外の値を返すために、アドレス演算子 \(`operator &`\) を再定義するクラスをラップするときに使用される簡単なテンプレートです。  このようなクラスの例としては、ATL の `CComBSTR`、`CComPtr`、および `CComQIPtr` クラス、そしてコンパイラ COM サポート クラスである `_com_ptr_t` が含まれます。  これらのクラスはすべて、いずれかのデータ メンバーのアドレスを返すために address\-of 演算子を再定義します \(`CComBSTR` の場合には `BSTR`、他のクラスの場合にはインターフェイス ポインター\)。  
  
 `CAdapt` の主な役割は、クラス `T` によって定義された address\-of 演算子を隠しながら、適合されたクラスの特性を保持することです。  `CAdapt` はこの役割を果たしており、型 `T` のパブリック メンバー [m\_T](../Topic/CAdapt::m_T.md) を保持し、変換演算子、比較演算子、およびコピー コンストラクターを定義することにより、まるで型 `T` のオブジェクトであるかのように `CAdapt` を特殊化できます。  
  
 アダプター クラス `CAdapt` は、いくつかの container\-style クラスで、含まれるオブジェクトのアドレスを address\-of 演算子を使用して取得できることが想定されているために、役立ちます。  address\-of 演算子の再定義によって、この要件に混乱が生じ、通常はコンパイル エラーが発生し、"単に動作" することが想定されているクラスで、適合されていない型の使用が妨げられることがあります。  `CAdapt` では、こうした問題を回避するための手段が提供されています。  
  
 通常 container\-style クラスでは、`CComBSTR`、`CComPtr`、`CComQIPtr`、または `_com_ptr_t` オブジェクトを保存する場合に `CAdapt` を使用します。  これは、C\+\+11 Standard のサポート前には C\+\+ Standard Library コンテナーで最も一般的に必要とされていましたが、C\+\+11 Standard Library コンテナーは `operator&()` をオーバーロードした型と共に自動的に動作します。  Standard Library では、オブジェクトの真のアドレスを取得するために内部で [std::addressof\(\)](../Topic/addressof.md) を使用することによりこれを実現しています。  
  
## 必要条件  
 **ヘッダー:** atlcomcli.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)