---
title: "BEGIN_ACCESSOR_MAP |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- BEGIN_ACCESSOR_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_ACCESSOR_MAP macro
ms.assetid: e6d6e3a4-62fa-4e49-8c53-caf8c9d20091
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0fd9684d3ab428ffa2e874f781208812d1ad12fc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="beginaccessormap"></a>BEGIN_ACCESSOR_MAP
アクセサー マップ エントリの開始位置を示します。  
  
## <a name="syntax"></a>構文  
  
```  
BEGIN_ACCESSOR_MAP(x, num)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *x*  
 [入力] ユーザー レコード クラスの名前。  
  
 *num*  
 [入力] このアクセサー マップのアクセサーの数。  
  
## <a name="remarks"></a>コメント  
 1 つの行セットで複数のアクセサーを使用する場合は、先頭に `BEGIN_ACCESSOR_MAP` を指定し、個々のアクセサーに対して `BEGIN_ACCESSOR` マクロを使用する必要があります。 `BEGIN_ACCESSOR` マクロは `END_ACCESSOR` マクロで終了します。 アクセサー マップは、 `END_ACCESSOR_MAP` マクロで終了します。  
  
 ユーザー レコードに含まれるアクセサーが 1 つのみの場合は、 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)マクロを使用します。  
  
## <a name="example"></a>例  

 ```cpp  
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
 ```

  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)