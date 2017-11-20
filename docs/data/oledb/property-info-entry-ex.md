---
title: "PROPERTY_INFO_ENTRY_EX |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROPERTY_INFO_ENTRY_EX
dev_langs: C++
helpviewer_keywords: PROPERTY_INFO_ENTRY_EX macro
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 61842dc963ae442d23f802c1fd64c037f4a882e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="propertyinfoentryex"></a>PROPERTY_INFO_ENTRY_EX
プロパティ セットの特定のプロパティを表します。  
  
## <a name="syntax"></a>構文  
  
```  
  
PROPERTY_INFO_ENTRY_EX(  
dwPropID  
, vt, dwFlags, value, options )  
```  
  
#### <a name="parameters"></a>パラメーター  
 *dwPropID*  
 [入力] プロパティ セット GUID と組み合わせて使用してプロパティを特定する [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) 値。  
  
 *vt*  
 [入力] このプロパティ エントリの [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 。  
  
 `dwFlags`  
 [入力] このプロパティ エントリを記述している [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) 値。  
  
 *値*  
 [入力] `DWORD`型のプロパティ値。  
  
 `options`  
 **DBPROPOPTIONS_REQUIRED** または **DBPROPOPTIONS_SETIFCHEAP**。 通常、 `options` はコンシューマーによって設定されるため、プロバイダーが設定する必要はありません。  
  
## <a name="remarks"></a>コメント  
 このマクロでは、オプションとフラグだけでなく、 `DWORD` 型のプロパティの値を直接指定できます。 単にプロパティを ATLDB.H に定義されている既定値に設定するには、 [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)を使用します。 オプションやフラグを設定せずに任意の値にプロパティを設定するには、 [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)を使用します。  
  
## <a name="example"></a>例  
 「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)