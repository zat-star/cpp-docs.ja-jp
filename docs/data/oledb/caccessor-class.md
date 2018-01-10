---
title: "CAccessor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
dev_langs: C++
helpviewer_keywords: CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f3f92d86ff67cc4ebfa752e84373c4f77bf3dc55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="caccessor-class"></a>CAccessor クラス
アクセサーの種類のいずれかを表します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      template < class   
      T  
       >  
class CAccessor : public CAccessorBase, public T  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ユーザー レコード クラスです。  
  
## <a name="remarks"></a>コメント  
 レコードがデータ ソースに静的にバインドされているときに使用されます。 レコードには、バッファーが含まれています。 このクラスは、行セットで複数のアクセサーをサポートします。  
  
 構造と、データベースの種類がわかっている場合に、このアクセサーの型を使用します。  
  
 アクセサーには、メモリを指しているフィールドが含まれている場合 (など、`BSTR`またはインターフェイス) する必要があります、メンバー関数を呼び出して、解放[caccessorrowset::freerecordmemory](../../data/oledb/caccessorrowset-freerecordmemory.md)レコードの読み取り、次の前にします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)