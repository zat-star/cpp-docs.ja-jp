---
title: "CPtrList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPtrList
dev_langs:
- C++
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7e69c8c0d80fea2720ea436bf0bff796ae57a60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cptrlist-class"></a>CPtrList クラス
void ポインターのリストをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CPtrList : public CObject  
```  
  
## <a name="members"></a>メンバー  
 メンバー関数は、`CPtrList`クラスのメンバー関数に似ています[CObList](../../mfc/reference/coblist-class.md)です。 メンバー関数については `CObList` クラスの説明を参照してください。 関数パラメーターまたは戻り値として `CObject` ポインターが使われている場合は、`void` へのポインターに置き換えます。  
  
 `CObject*& CObList::GetHead() const;`  
  
 たとえば、次のように変換します。  
  
 `void*& CPtrList::GetHead() const;`  
  
## <a name="remarks"></a>コメント  
 `CPtrList` には、`IMPLEMENT_DYNAMIC` マクロが組み込まれているので、`CDumpContext` オブジェクトへのランタイム型のアクセスとダンプをサポートします。 ポインター リストの各要素をダンプする必要があるときは、ダンプ コンテキストの深さを 1 以上に設定する必要があります。  
  
 ポインター リストはシリアル化できません。  
  
 `CPtrList` オブジェクトが削除されたとき、またはその要素が削除されたときは、ポインターだけが削除されます。ポインターが参照するエンティティは削除されません。  
  
 使用する方法についての`CPtrList`、記事を参照して[コレクション](../../mfc/collections.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcoll.h  
  
## <a name="see-also"></a>参照  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObList クラス](../../mfc/reference/coblist-class.md)
