---
title: "Cdynamicparameteraccessor::getparamstring |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
dev_langs: C++
helpviewer_keywords: GetParamString method
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ed04d3258ad5f4d5ed68a32b32923432577453ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorgetparamstring"></a>CDynamicParameterAccessor::GetParamString
バッファーに格納され、指定されたパラメーターの文字列データを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringA& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringW& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nParam`  
 [in]パラメーターの数 (1 からのオフセット)。 に対するパラメーター 0 は、戻り値に予約されています。 パラメーター数は、SQL またはストアド プロシージャの呼び出しでその順序に基づいて、パラメーターのインデックスです。 参照してください[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)例についてはします。  
  
 `strOutput`  
 [out]ANSI (**CSimpleStringA**) または Unicode (**CSimpleStringW**) 文字列型の指定されたパラメーターのデータ。 型のパラメーターを渡す必要があります`CString`、例を示します。  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 [out]ANSI へのポインター (**CHAR**) または Unicode (**WCHAR**) 文字列型の指定されたパラメーターのデータ。  
  
 `pMaxLen`  
 [out]バッファーのサイズへのポインターが指す`pBuffer`(文字を含む、終端の NULL)。  
  
## <a name="remarks"></a>コメント  
 返します**true**成功した場合または**false**エラー発生時にします。  
  
 場合`pBuffer`が NULL の場合、このメソッドが指すメモリに必要なバッファー サイズを設定`pMaxLen`を返すと**true**データをコピーすることがなくです。  
  
 このメソッドが失敗バッファー`pBuffer`文字列全体を格納するのに十分な大きさではありません。  
  
 使用して`GetParamString`バッファーから文字列パラメーターのデータを取得します。 使用して[GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md)バッファーから文字列以外のパラメーターのデータを取得します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)