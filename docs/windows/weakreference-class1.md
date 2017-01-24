---
title: "WeakReference クラス | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::WeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakReference クラス"
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakReference クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
class WeakReference;  
```  
  
## 解説  
 Windows ランタイムまたは標準的な COM で使用できる *弱い参照を* 表します。  弱い参照はアクセスできないか、ことができるオブジェクトを表します。  
  
 `WeakReference` オブジェクトがオブジェクトへのポインターであるか、強い参照の部数である *強い参照カウントを*保持し、*強い参照*解決 \(\) メソッドによって配布。  強い参照カウントが 0 以外のな間、強い参照が有効であり、オブジェクトにアクセスできます。  強い参照カウントがゼロになると、強い参照は無効であり、オブジェクトはアクセスできません。  
  
 WeakReference オブジェクトは、通常、プロシージャが外部スレッドまたはアプリケーションによって制御されるオブジェクトを表すために使用されます。  たとえば、"からファイル オブジェクトへの WeakReference オブジェクトを構築します。  ファイルを開いているとき、強い参照が有効です。  ただし、ファイルを閉じると、強い参照が無効になります。  
  
 WeakReference のメソッドはスレッド セーフです。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[WeakReference::WeakReference コンストラクター](../windows/weakreference-weakreference-constructor.md)|WeakReference クラスの新しいインスタンスを初期化します。|  
|[WeakReference::~WeakReference デストラクター](../windows/weakreference-tilde-weakreference-destructor.md)|Deinitializes \(破棄\) WeakReference クラスの現在のインスタンス。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[WeakReference::DecrementStrongReference メソッド](../Topic/WeakReference::DecrementStrongReference%20Method.md)|WeakReference の現在のオブジェクトの強い参照カウントをデクリメントします。|  
|[WeakReference::IncrementStrongReference メソッド](../windows/weakreference-incrementstrongreference-method.md)|WeakReference の現在のオブジェクトの強い参照カウントをインクリメントします。|  
|[WeakReference::Resolve メソッド](../windows/weakreference-resolve-method.md)|強い参照カウントが 0 以外のは現在の強い参照値に指定したポインターを設定します。|  
|[WeakReference::SetUnknown メソッド](../windows/weakreference-setunknown-method.md)|指定されたインターフェイス ポインターへの WeakReference の現在のオブジェクトの強い参照を設定します。|  
  
## 継承階層  
 `WeakReference`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)