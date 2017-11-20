---
title: "RuntimeClass クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass
dev_langs: C++
helpviewer_keywords: RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e757712b360ff3ed4de12d8236c75a691a1f0c7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclass-class"></a>RuntimeClass クラス
指定した数のインターフェイスを継承し、指定した Windows ランタイム、クラシック COM、および弱い参照をサポートする、インスタンス化されたクラスを表します。  
  
 通常、WRL 型は `RuntimeClass` から派生します。これは、このクラスで `AddRef`、`Release`、および `QueryInterface` が実装され、モジュールの全体的な参照カウントを管理できるためです。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
class RuntimeClass : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT, RuntimeClassFlags<WinRt>>;  
  
template <  
   unsigned int classFlags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
class RuntimeClass<RuntimeClassFlags<classFlags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT, RuntimeClassFlags<classFlags> >;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `I0`  
 0 番目のインターフェイス ID です  (必須)。  
  
 `I1`  
 1 番目のインターフェイス ID です  (オプション)。  
  
 `I2`  
 2 番目のインターフェイス ID です  (オプション)。  
  
 `I3`  
 3 番目のインターフェイス ID です  (オプション)。  
  
 `I4`  
 4 番目のインターフェイス ID です  (オプション)。  
  
 `I5`  
 5 番目のインターフェイス ID です  (オプション)。  
  
 `I6`  
 6 番目のインターフェイス ID です  (オプション)。  
  
 `I7`  
 7 番目のインターフェイス ID です  (オプション)。  
  
 `I8`  
 8 番目のインターフェイス ID です  (オプション)。  
  
 `I9`  
 9 番目のインターフェイス ID です  (オプション)。  
  
 `classFlags`  
 1 つまたは複数の組み合わせ[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。  `__WRL_CONFIGURATION_LEGACY__` ClassFlags プロジェクト内のすべてのランタイム クラスの既定値を変更するマクロを定義することができます。 、定義されている場合、RuntimeClass インスタンスは、非アジャイル dy 既定がします。 定義されていない場合、RuntimeClass インスタンスは、既定でアジャイルです。 あいまいさを避けるために、RuntimeClassType::FtmBase または RuntimeClassType::InhibitFtmBase が常に指定します。
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[RuntimeClass::RuntimeClass コンストラクター](../windows/runtimeclass-runtimeclass-constructor.md)|RuntimeClass クラスの現在のインスタンスを初期化します。|  
|[RuntimeClass::~RuntimeClass デストラクター](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|RuntimeClass クラスの現在のインスタンスの初期化を解除します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `RuntimeClass`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)
