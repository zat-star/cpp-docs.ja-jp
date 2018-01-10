---
title: "TerminateMap 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::TerminateMap
dev_langs: C++
helpviewer_keywords: TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 42f71f86dce35457d5efa81c28d2a58106ba5b81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="terminatemap-function"></a>TerminateMap 関数
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
## <a name="parameters"></a>パラメーター  
 `module`  
 A[モジュール](../windows/module-class.md)です。  
  
 `serverName`  
 パラメーターで指定されたモジュールでクラス ファクトリのサブセットの名前`module`です。  
  
 `forceTerminate`  
 `true`クラスを終了するに関係なく、ファクトリはアクティブです。`false`ファクトリがアクティブな場合、クラス ファクトリを終了します。  
  
## <a name="return-value"></a>戻り値  
 `true`すべてのクラス ファクトリを終了しました。 場合、それ以外の場合、`false`です。  
  
## <a name="remarks"></a>コメント  
 指定されたモジュールでクラス ファクトリを終了します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)