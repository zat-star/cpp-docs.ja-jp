---
title: "Module::GenericReleaseNotifier クラス | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::GenericReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GenericReleaseNotifier クラス"
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::GenericReleaseNotifier クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在のモジュール内の最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。 イベント ハンドラーは、ラムダ、ファンクタ、または関数へのポインターによって指定されます。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   typename T  
>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 イベント ハンドラーの場所が含まれているデータ メンバーの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::GenericReleaseNotifier コンス トラクター](../Topic/Module::GenericReleaseNotifier::GenericReleaseNotifier%20Constructor.md)|Module::genericreleasenotifier クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Module::genericreleasenotifier:: メソッドを呼び出す](../windows/module-genericreleasenotifier-invoke-method.md)|Module::genericreleasenotifier の現在のオブジェクトに関連付けられているイベント ハンドラーを呼び出します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::callback_ データ メンバー](../windows/module-genericreleasenotifier-callback-data-member.md)|ラムダ、ファンクタ、または現在の module::genericreleasenotifier オブジェクトに関連付けられている関数へのポインター イベント ハンドラーを保持します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [モジュール クラス](../windows/module-class.md)