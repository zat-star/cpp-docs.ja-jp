---
title: "WeakRef::CopyTo メソッド | Microsoft Docs"
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
  - "client/Microsoft::WRL::WeakRef::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo メソッド"
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
caps.latest.revision: 5
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef::CopyTo メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

使用可能なインターフェイスへのポインターがあるなら、指定されたポインター変数にそれを割り当てます。  
  
## 構文  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<  
   typename U  
>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### パラメーター  
 `U`  
 IInspectable インターフェイスへのポインター。`U` が IInspectable から派生していない場合、エラーが発生します。  
  
 `riid`  
 インターフェイス ID。`riid` が **IWeakReference** から派生していない場合、エラーが発生します。  
  
 `ptr`  
 IInspectable または IWeakReference への二重間接ポインター。  
  
## 戻り値  
 成功した場合は S\_OK、そうでない場合は失敗を示す HRESULT。 詳細については、「解説」を参照してください。  
  
## コメント  
 S\_OK の戻り値はこの操作が成功したことを示しますが、弱い参照が強い参照に解決されたかどうかは示していません。 S\_OK が返される場合は、そのパラメーター `p` が強力な参照であること、つまりパラメーター `p` が `nullptr` と等しくないことをテストします。  
  
 Windows 10 SDK 以降では、弱い参照を取得できなかった場合、このメソッドは WeakRef インスタンスを `nullptr` に設定しません。このため、WeakRef が `nullptr` かどうかを確認するエラー チェック コードは避けてください。 代わりに、返された HRESULT を確認してメソッドが成功したかどうかを判別するか、`ptr` が `nullptr` かどうかを確認します。  
  
## 必要条件  
 **ヘッダー:**  client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [WeakRef クラス](../windows/weakref-class.md)