---
title: "ComPtr クラス | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtr クラス"
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート パラメーターで指定されたインターフェイスを表す*スマート ポインター*型を作成します。 ComPtr は、基になるインターフェイス ポインターの参照カウントを自動的に維持し、参照カウントがゼロになるとそのインターフェイスを解放します。  
  
## 構文  
  
```  
template <  
   typename T  
>  
class ComPtr;  
  
template<  
   class U  
>  
friend class ComPtr;  
```  
  
#### パラメーター  
 `T`  
 ComPtr が表すインターフェイス。  
  
 `U`  
 現在の ComPtr がフレンドであるクラス  \(このパラメーターを使用するテンプレートは保護されています\)。  
  
## コメント  
 ComPtr \<\> は、基になるインターフェイス ポインターを表す型を宣言します。 ComPtr \<\> を使用して変数を宣言してから、矢印のメンバー アクセス演算子 \(`->`\) を使用してインターフェイス メンバー関数にアクセスします。  
  
 スマート ポインターの詳細については、MSDN ライブラリの [COM Coding Practices](http://msdn.microsoft.com/ja-jp/76aca556-b4d6-4e67-a2a3-4439900f0c39) トピックで「COM スマート ポインター」のサブセクションを参照してください。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`InterfaceType`|`T` テンプレート パラメーターで指定された型のシノニム。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[ComPtr::ComPtr コンストラクター](../windows/comptr-comptr-constructor.md)|ComPtr クラスの新しいインスタンスを初期化します。 オーバーロードは、既定、コピー、移動、および変換の各コンストラクターを提供します。|  
|[ComPtr::~ComPtr デストラクター](../windows/comptr-tilde-comptr-destructor.md)|ComPtr のインスタンスを初期化解除します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ComPtr::As メソッド](../windows/comptr-as-method.md)|指定されたテンプレート パラメーターで識別されるインターフェイスを表す ComPtr オブジェクトを返します。|  
|[ComPtr::AsIID メソッド](../windows/comptr-asiid-method.md)|指定されたインターフェイス ID で識別されるインターフェイスを表す ComPtr オブジェクトを返します。|  
|[ComPtr::AsWeak メソッド](../windows/comptr-asweak-method.md)|現在のオブジェクトへの弱い参照を取得します。|  
|[ComPtr::Attach メソッド](../windows/comptr-attach-method.md)|この ComPtr と、現在のテンプレート型パラメーターで指定されたインターフェイスの種類を関連付けます。|  
|[ComPtr::CopyTo メソッド](../windows/comptr-copyto-method.md)|この ComPtr に関連付けられた現在のまたは指定されたインターフェイスを、指定された出力ポインターにコピーします。|  
|[ComPtr::Detach メソッド](../Topic/ComPtr::Detach%20Method.md)|この ComPtr が表すインターフェイスからその関連付けを解除します。|  
|[ComPtr::Get メソッド](../windows/comptr-get-method.md)|この ComPtr に関連付けられたインターフェイスへのポインターを取得します。|  
|[ComPtr::GetAddressOf メソッド](../Topic/ComPtr::GetAddressOf%20Method.md)|[ptr\_](../windows/comptr-ptr-data-member.md) データ メンバーのアドレスを取得します。これには、この ComPtr によって表されるインターフェイスへのポインターが含まれています。|  
|[ComPtr::ReleaseAndGetAddressOf メソッド](../windows/comptr-releaseandgetaddressof-method.md)|この ComPtr に関連付けられたインターフェイスを解放してから、[ptr\_](../windows/comptr-ptr-data-member.md) データ メンバーのアドレスを取得します。このアドレスには、解放されたインターフェイスへのポインターが含まれています。|  
|[ComPtr::Reset](../windows/comptr-reset.md)|この ComPtr に関連付けられているインターフェイスを指すポインターへのすべての参照を解放します。|  
|[ComPtr::Swap メソッド](../windows/comptr-swap-method.md)|指定された ComPtr によって管理されているインターフェイスと現在の ComPtr によって管理されるインターフェイスを交換します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[ComPtr::InternalAddRef メソッド](../windows/comptr-internaladdref-method.md)|この ComPtr に関連付けられたインターフェイスの参照カウントをインクリメントします。|  
|[ComPtr::InternalRelease メソッド](../windows/comptr-internalrelease-method.md)|この ComPtr に関連付けられたインターフェイスに対して COM 解放操作を実行します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[ComPtr::operator Microsoft::WRL::Details::BoolType 演算子](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|ComPtr がインターフェイスのオブジェクト有効期間を管理しているかどうかを示します。|  
|[ComPtr::operator& 演算子](../windows/comptr-operator-ampersand-operator.md)|現在の ComPtr のアドレスを取得します。|  
|[ComPtr::operator\= 演算子](../windows/comptr-operator-assign-operator.md)|値を現在の ComPtr に割り当てます。|  
|[ComPtr::operator\-\> 演算子](../windows/comptr-operator-arrow-operator.md)|現在のテンプレート パラメーターで指定された型へのポインターを取得します。|  
|[ComPtr::operator\=\= 演算子](../windows/comptr-operator-equality-operator.md)|2 つの ComPtr オブジェクトが等しいかどうかを示します。|  
|[ComPtr::operator\!\= 演算子](../windows/comptr-operator-inequality-operator.md)|2 つの ComPtr オブジェクトが等しくないかどうかを示します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[ComPtr::ptr\_ データ メンバー](../windows/comptr-ptr-data-member.md)|この ComPtr に関連付けられ、管理されているインターフェイスへのポインターが含まれています。|  
  
## 継承階層  
 `ComPtr`  
  
## 必要条件  
 **ヘッダー:**  client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)