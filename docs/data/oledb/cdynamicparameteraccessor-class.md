---
title: "CDynamicParameterAccessor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/14/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18f53ca6d95d215ad41c6b2501245be0e470bbb1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor クラス

ような[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)を呼び出すことによって設定するパラメーター情報を取得するが、 [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters)インターフェイスです。

## <a name="syntax"></a>構文

```cpp
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

このクラスを使用して、SQL Server のストアド プロシージャを実行し、出力パラメーターの値を取得する方法を示す例について、次を参照してください、 [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)のサンプル コードでは、 [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) 。GitHub のリポジトリ。

## <a name="requirements"></a>必要条件

**ヘッダー**: atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)  
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)  
[CAccessor クラス](../../data/oledb/caccessor-class.md)  
[CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)  
[CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)  
