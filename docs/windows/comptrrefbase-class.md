---
title: "ComPtrRefBase クラス | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRefBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtrRefBase クラス"
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRefBase クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### パラメーター  
 `T`  
 ここからは、派生されない [ComPtr\<T\>](../windows/comptr-class.md) の型または型の ComPtr オブジェクトで表されるインターフェイス。  
  
## 解説  
 [ComPtrRef](../Topic/ComPtrRef%20Class.md) クラスの基本クラスを表します。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`InterfaceType`|テンプレート パラメーター `T`の型のシノニムです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[ComPtrRefBase::operator IInspectable\*\* 演算子](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|IInspectable インターフェイス ポインターへのポインター上には [ptr\_](../windows/comptrrefbase-ptr-data-member.md) の現在のデータ メンバーをキャストします。|  
|[ComPtrRefBase::operator IUnknown\*\* 演算子](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|IUnknown インターフェイス ポインターへのポインター上には [ptr\_](../windows/comptrrefbase-ptr-data-member.md) の現在のデータ メンバーをキャストします。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[ComPtrRefBase::ptr\_ データ メンバー](../windows/comptrrefbase-ptr-data-member.md)|現在のテンプレート パラメーターによって指定された型へのポインター。|  
  
## 継承階層  
 `ComPtrRefBase`  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)