---
title: "Irowsetimpl::m_breset |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
dev_langs: C++
helpviewer_keywords: m_bReset
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4323d92398ea4d47410a2b5a3aad08972628634d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplmbreset"></a>IRowsetImpl::m_bReset
行セットのカーソル位置が定義されているかどうかを判断するために使用するビット フラグです。  
  
## <a name="syntax"></a>構文  
  
```  
  
unsigned m_bReset:1;  
  
```  
  
## <a name="remarks"></a>コメント  
 コンシューマーを呼び出す場合[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) 、負の値と`lOffset`または*cRows*と`m_bReset`が true の場合、`GetNextRows`行セットの末尾に移動します。 場合`m_bReset`が false の場合、コンシューマーが、OLE DB 仕様に準拠して、エラー コードを受信します。 `m_bReset`フラグを取得設定**true**行セットを初めて作成すると、コンシューマーが呼び出したとき[irowsetimpl::restartposition](../../data/oledb/irowsetimpl-restartposition.md)です。 セットが取得**false**を呼び出すと`GetNextRows`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)