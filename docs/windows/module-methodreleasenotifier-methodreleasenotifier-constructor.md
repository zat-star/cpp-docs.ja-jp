---
title: "Module::MethodReleaseNotifier::MethodReleaseNotifier コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MethodReleaseNotifier、コンストラクター"
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Module::MethodReleaseNotifier::MethodReleaseNotifier コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Module::MethodReleaseNotifier クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
#### パラメーター  
 `object`  
 メンバー関数がイベント ハンドラーであるオブジェクト。  
  
 `method`  
 イベント ハンドラーのパラメーター `object` のメンバー関数。  
  
 `release`  
 [Module::ReleaseNotifier::Release \(\)](../windows/module-releasenotifier-release.md) の基本メソッドの呼び出しを有効にするに `true` ;を指定します。それ以外の場合は `false`を指定します。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Module::MethodReleaseNotifier クラス](../Topic/Module::MethodReleaseNotifier%20Class.md)