---
title: "WeakRef::As メソッド | Microsoft Docs"
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
  - "client/Microsoft::WRL::WeakRef::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As メソッド"
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
caps.latest.revision: 6
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef::As メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定された ComPtr ポインター パラメーターを、指定されたインターフェイスを表すように設定します。  
  
## 構文  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
#### パラメーター  
 `U`  
 インターフェイス ID。  
  
 `ptr`  
 この操作の完了時の、パラメーター `U` を表すオブジェクト。  
  
## 戻り値  
  
-   この操作が成功すると S\_OK になります。失敗すると HRESULT \(操作が失敗した理由を示す\) になり、`ptr` は `nullptr` に設定されます。  
  
-   この操作が成功すると S\_OK になりますが、現在の WeakRef オブジェクトは既に解放されています。 パラメーター `ptr` は `nullptr` に設定されます。  
  
-   この操作が成功すると S\_OK になりますが、現在の WeakRef オブジェクトはパラメーター `U` から派生しません。 パラメーター `ptr` は `nullptr` に設定されます。  
  
## コメント  
 `U` が IWeakReference の場合、エラーが生成されます。あるいは、IInspectable から派生しません。  
  
 最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレートは、[auto](../cpp/auto-cpp.md) 型推論キーワードなどの C\+\+ 言語の機能をサポートしている内部ヘルパーの特殊化です。  
  
 Windows 10 SDK 以降では、弱い参照を取得できなかった場合、このメソッドは WeakRef インスタンスを `nullptr` に設定しません。そのため、`nullptr` の WeakRef を確認するエラー チェック コードは避けてください。 代わりに、返された HRESULT を確認してメソッドが成功したかどうかを判別するか、`nullptr` について、`ptr` を確認します。  
  
## 必要条件  
 **ヘッダー:**  client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [WeakRef クラス](../windows/weakref-class.md)