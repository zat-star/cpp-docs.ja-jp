---
title: "Cdbpropset::addproperty |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
dev_langs:
- C++
helpviewer_keywords:
- AddProperty method
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d71e3e2b86c631cc2e9d0a3516c46cb418737d7b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cdbpropsetaddproperty"></a>CDBPropSet::AddProperty
プロパティ セットに、プロパティを追加します。  
  
## <a name="syntax"></a>構文  
  
```
bool AddProperty(DWORD dwPropertyID,   
   constVARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   LPCSTR szValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   LPCWSTR szValue,DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   bool bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   BYTE bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   short nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   long nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   float fltValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   double dblValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   CY cyValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *dwPropertyID*  
 [in]追加するプロパティの ID。 初期化するために使用される、 **dwPropertyID**の`DBPROP`構造、プロパティ セットに追加します。  
  
 `var`  
 [in]バリアント型のプロパティの値を初期化するために使用される、`DBPROP`構造、プロパティ セットに追加します。  
  
 `szValue`  
 [in]プロパティの値を初期化するために使用する文字列、`DBPROP`構造、プロパティ セットに追加します。  
  
 `bValue`  
 [in]A**バイト**またはのプロパティの値を初期化するために使用されるブール値、`DBPROP`構造、プロパティ セットに追加します。  
  
 `nValue`  
 [in]プロパティの値を初期化するために使用される整数値、`DBPROP`構造、プロパティ セットに追加します。  
  
 *fltValue*  
 [in]浮動小数点値のプロパティの値を初期化するために使用される、`DBPROP`構造、プロパティ セットに追加します。  
  
 `dblValue`  
 [in]倍精度浮動小数点値のプロパティの値を初期化するために使用される、`DBPROP`構造、プロパティ セットに追加します。  
  
 `cyValue`  
 [in]プロパティの値を初期化するために使用される CY 通貨値、`DBPROP`構造、プロパティ セットに追加します。  
  
## <a name="return-value"></a>戻り値  
 **true**場合は、プロパティが正常に追加します。 それ以外の場合、 **false**です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDBPropSet クラス](../../data/oledb/cdbpropset-class.md)   
 [DBPROP 構造体](https://msdn.microsoft.com/en-us/library/ms717970.aspx)