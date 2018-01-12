---
title: "Cdynamicparameteraccessor::setparamstring |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
dev_langs: C++
helpviewer_keywords: SetParamString method
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75d6e9887b609349a092bb67e55508ca1429387b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorsetparamstring"></a>CDynamicParameterAccessor::SetParamString
バッファーに格納され、指定されたパラメーターの文字列データを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      bool SetParamString(   
   DBORDINAL nParam,   
   const CHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
bool SetParamString(   
   DBORDINAL nParam,   
   const WCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 参照してください[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)例についてはします。  
  
 `pString`  
 [in]ANSI へのポインター (**CHAR**) または Unicode (**WCHAR**) 文字列型の指定されたパラメーターのデータ。 参照してください`DBSTATUS`oledb.h でします。  
  
 *status*  
 [in]`DBSTATUS`指定されたパラメーターの状態。 詳細について`DBSTATUS`値を参照してください[ステータス](https://msdn.microsoft.com/en-us/library/ms722617.aspx)で、 *OLE DB プログラマーズ リファレンス*、または検索`DBSTATUS`oledb.h でします。  
  
## <a name="remarks"></a>コメント  
 返します**true**成功した場合または**false**エラー発生時にします。  
  
 `SetParamString`指定された最大サイズを超える文字列を設定しようとする場合は失敗`pString`です。  
  
 使用して`SetParamString`をバッファーに文字列パラメーターのデータを設定します。 使用して[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)をバッファーに文字列以外のパラメーターのデータを設定します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)