---
title: "CComPtr クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtr クラス"
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComPtr クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。  
  
## 構文  
  
```  
  
      template<  
   class T   
>  
class CComPtr  
```  
  
#### パラメーター  
 `T`  
 COM を格納するポインターの型を指定することを実装します。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)|コンストラクターです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CComPtr::operator \=](../Topic/CComPtr::operator%20=.md)|メンバーのポインターにポインターを割り当てます。|  
  
## 解説  
 ATL を使用 `CComPtr` と [CComQIPtr](../../atl/reference/ccomqiptr-class.md) は、COM を管理するポインターを実装します。  両方の [CComPtrBase](../../atl/reference/ccomptrbase-class.md)から派生し、両方の自動参照カウントを実行します。  
  
 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) の **CComPtr** とクラスは自動参照カウントを実行して、メモリ リークの削除を行うことができます。  次の関数は、同じ論理演算を実行します; ただし、2 番目のバージョンが **CComPtr** のクラスを使用してエラーも発生の可能性があるか、メモ:  
  
 [!CODE [NVC_ATL_Utilities#130](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#130)]  
  
 [!CODE [NVC_ATL_Utilities#131](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#131)]  
  
 デバッグ ビルドでは、コードのトレースのリンク atlsd.lib。  
  
## 継承階層  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [クラスの概要](../../atl/atl-class-overview.md)