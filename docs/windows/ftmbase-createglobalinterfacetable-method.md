---
title: "Ftmbase::createglobalinterfacetable メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable
dev_langs: C++
helpviewer_keywords: CreateGlobalInterfaceTable method
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc96d8eaff3def90f9ff3e9bd76e0ef067094715
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasecreateglobalinterfacetable-method"></a>FtmBase::CreateGlobalInterfaceTable メソッド
グローバル インターフェイス テーブル (GIT) を作成します。  
  
## <a name="syntax"></a>構文  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `git`  
 この操作の完了時、グローバル インターフェイス テーブルへのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="remarks"></a>コメント  
 詳細については、MSDN ライブラリの「COM リファレンス」トピックの"COM インターフェイス"サブトピック「"については」のトピックを参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [FtmBase クラス](../windows/ftmbase-class.md)