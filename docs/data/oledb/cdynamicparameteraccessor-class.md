---
title: "CDynamicParameterAccessor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
dev_langs: C++
helpviewer_keywords: CDynamicParameterAccessor class
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e30e003a054c6806994780fd4bd7b5af24f946a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor クラス
[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) と類似していますが、 [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) インターフェイスを呼び出すことで設定されるパラメーター情報を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDynamicParameterAccessor : public CDynamicAccessor  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-cdynamicparameteraccessor.md)|コンストラクターです。|  
|[GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md)|バッファーからパラメーター データを取得します。|  
|[GetParamCount](../../data/oledb/cdynamicparameteraccessor-getparamcount.md)|アクセサー内のパラメーターの数を取得します。|  
|[GetParamIO](../../data/oledb/cdynamicparameteraccessor-getparamio.md)|指定されたパラメーターが入力または出力パラメーターであるかどうかを判断します。|  
|[GetParamLength](../../data/oledb/cdynamicparameteraccessor-getparamlength.md)|バッファーに格納され、指定されたパラメーターの長さを取得します。|  
|[GetParamName](../../data/oledb/cdynamicparameteraccessor-getparamname.md)|指定されたパラメーターの名前を取得します。|  
|[GetParamStatus](../../data/oledb/cdynamicparameteraccessor-getparamstatus.md)|バッファーに格納され、指定されたパラメーターのステータスを取得します。|  
|[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)|バッファーに格納され、指定されたパラメーターの文字列データを取得します。|  
|[GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)|指定されたパラメーターのデータ型を取得します。|  
|[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)|パラメーター データを使用してバッファーを設定します。|  
|[SetParamLength](../../data/oledb/cdynamicparameteraccessor-setparamlength.md)|バッファーに格納され、指定されたパラメーターの長さを設定します。|  
|[SetParamStatus](../../data/oledb/cdynamicparameteraccessor-setparamstatus.md)|バッファーに格納され、指定されたパラメーターのステータスを設定します。|  
|[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)|バッファーに格納され、指定されたパラメーターの文字列データを設定します。|  
  
## <a name="remarks"></a>コメント  
 コンシューマーがこのクラスを使用するには、プロバイダーで `ICommandWithParameters` がサポートされている必要があります。  
  
 パラメーター情報は、このクラスによって作成および管理されるバッファーに格納されます。 [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) と [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)を使用してバッファーからパラメーター データを取得します。  
  
 このクラスを使用して SQL Server のストアド プロシージャを実行し、出力パラメーター値を取得する方法の例については、サポート技術情報の記事 Q058860 の「HOWTO: Execute Stored Procedure using CDynamicParameterAccessor」を参照してください。 サポート技術情報の記事は、MSDN ライブラリの Visual Studio マニュアルまたは [http://support.microsoft.com/](http://support.microsoft.com)で参照できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー**: atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)