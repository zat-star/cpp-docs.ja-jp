---
title: "WeakRef::AsIID メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID メソッド"
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# WeakRef::AsIID メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したインターフェイス ID を表すよう指定された ComPtr ポインター パラメーターを設定します。  
  
## 構文  
  
```  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
#### パラメーター  
 `riid`  
 インターフェイス ID。  
  
 `ptr`  
 この操作の完了時の、パラメーター `riid` を表すオブジェクト。  
  
## 戻り値  
  
-   この操作が成功すると S\_OK になります。失敗すると HRESULT \(操作が失敗した理由を示す\) になり、`ptr` は `nullptr` に設定されます。  
  
-   この操作が成功すると S\_OK になりますが、現在の WeakRef オブジェクトは既に解放されています。 パラメーターを `ptr` を `nullptr` に設定します。  
  
-   この操作が成功すると S\_OK になりますが、現在の WeakRef オブジェクトはパラメーター `riid` から派生しません。 パラメーター `ptr` は `nullptr` に設定されます。 \(詳細については、「解説」を参照してください。\)  
  
## コメント  
 パラメーター `riid` が IInspectable から派生していない場合、エラーが発生します。 このエラーは、戻り値よりも優先されます。  
  
 最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレート \(ここでは示されていないが、ヘッダー ファイルでは宣言されている\) は、[auto](../cpp/auto-cpp.md) 型推論キーワードなどの C\+\+ 言語の機能をサポートしている内部ヘルパーの特殊化です。  
  
 Windows 10 SDK 以降では、弱い参照を取得できなかった場合、このメソッドは WeakRef インスタンスを `nullptr` に設定しません。そのため、`nullptr` の WeakRef を確認するエラー チェック コードは避けてください。 代わりに、返された HRESULT を確認してメソッドが成功したかどうかを判別するか、`nullptr` について、`ptr` を確認します。  
  
## 必要条件  
 **ヘッダー:**  client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [WeakRef クラス](../windows/weakref-class.md)