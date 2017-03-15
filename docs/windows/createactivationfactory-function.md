---
title: "CreateActivationFactory 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreateActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateActivationFactory 関数"
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# CreateActivationFactory 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows ランタイムで処理できる指定されたクラスのインスタンスを作成するファクトリを作成します。  
  
## 構文  
  
```cpp  
  
template<typename Factory>  
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(  
      _In_ unsigned int *flags,    
      _In_ const CreatorMap* entry,   
      REFIID riid,   
     _Outptr_ IUnknown **ppFactory) throw();  
  
```  
  
#### パラメーター  
 `flags`  
 1 つ以上の [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 列挙値の組み合わせです。  
  
 `entry`  
 パラメーター `riid`についての初期化と登録情報を含む [CreatorMap](../windows/creatormap-structure.md) へのポインター。  
  
 `riid`  
 インターフェイス ID への参照。  
  
 `ppFactory`  
 この操作が正常に完了すると、アクティベーション ファクトリへのポインター。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す HRESULT を返します。  
  
## 解説  
 Assert のエラーは、テンプレート パラメーター `Factory` がインターフェイス IActivationFactory から派生しなければ表示されます。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)