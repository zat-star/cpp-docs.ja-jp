---
title: "Module::Create メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::Create"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Create メソッド"
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module::Create メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

モジュールのインスタンスを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW static Module& Create();  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 モジュール型。  
  
 `callback`  
 モジュールの最後のインスタンス オブジェクトがリリースされたときに呼び出されます。  
  
 `object`  
  `object` と `method` パラメーターの組み合わせで使用されます。 ポイント最後のインスタンス オブジェクト、モジュールの最後のインスタンス オブジェクトが離されるとします。  
  
 `method`  
  `object` と `method` パラメーターの組み合わせで使用されます。 モジュールの最後のインスタンス オブジェクトがリリースされたときに、最後のインスタンス オブジェクトのメソッドを指します。  
  
## <a name="return-value"></a>戻り値  
 モジュールへの参照。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>「  
[モジュール クラス](../windows/module-class.md)

 