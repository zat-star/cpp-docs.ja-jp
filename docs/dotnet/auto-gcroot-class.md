---
title: "auto_gcroot クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs: C++
helpviewer_keywords: auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bb203193d1568056c631d90a2e1f5b1cf1d00e5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="autogcroot-class"></a>auto_gcroot クラス
自動リソース管理 (と同様に[auto_ptr クラス](../standard-library/auto-ptr-class.md)) をネイティブ型に仮想のハンドルを埋め込むには使用できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_element_type`  
 埋め込まれるマネージ型です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー ファイル** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>参照  
 [auto_gcroot](../dotnet/auto-gcroot.md)   
 [auto_gcroot メンバー](../dotnet/auto-gcroot-members.md)   
 [方法: ネイティブ型のハンドルを宣言します。](../dotnet/how-to-declare-handles-in-native-types.md)   
 [auto_handle クラス](../dotnet/auto-handle-class.md)