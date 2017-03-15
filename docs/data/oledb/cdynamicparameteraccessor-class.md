---
title: "CDynamicParameterAccessor クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDynamicParameterAccessor"
  - "ATL::CDynamicParameterAccessor"
  - "CDynamicParameterAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicParameterAccessor クラス"
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# CDynamicParameterAccessor クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) と類似していますが、[ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) インターフェイスを呼び出すことで設定されるパラメーター情報を取得します。  
  
## 構文  
  
```  
class CDynamicParameterAccessor : public CDynamicAccessor  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-cdynamicparameteraccessor.md)|コンストラクターです。|  
|[GetParam](../Topic/CDynamicParameterAccessor::GetParam.md)|バッファーからパラメーター データを取得します。|  
|[GetParamCount](../../data/oledb/cdynamicparameteraccessor-getparamcount.md)|アクセサー内のパラメーターの数を取得します。|  
|[GetParamIO](../../data/oledb/cdynamicparameteraccessor-getparamio.md)|指定されたパラメーターが入力または出力パラメーターであるかどうかを判断します。|  
|[GetParamLength](../Topic/CDynamicParameterAccessor::GetParamLength.md)|バッファーに格納され、指定されたパラメーターの長さを取得します。|  
|[GetParamName](../../data/oledb/cdynamicparameteraccessor-getparamname.md)|指定されたパラメーターの名前を取得します。|  
|[GetParamStatus](../../data/oledb/cdynamicparameteraccessor-getparamstatus.md)|バッファーに格納され、指定されたパラメーターのステータスを取得します。|  
|[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)|バッファーに格納され、指定されたパラメーターの文字列データを取得します。|  
|[GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)|指定されたパラメーターのデータ型を取得します。|  
|[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)|パラメーター データを使用してバッファーを設定します。|  
|[SetParamLength](../../data/oledb/cdynamicparameteraccessor-setparamlength.md)|バッファーに格納され、指定されたパラメーターの長さを設定します。|  
|[SetParamStatus](../../data/oledb/cdynamicparameteraccessor-setparamstatus.md)|バッファーに格納され、指定されたパラメーターのステータスを設定します。|  
|[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)|バッファーに格納され、指定されたパラメーターの文字列データを設定します。|  
  
## 解説  
 コンシューマーがこのクラスを使用するには、プロバイダーで `ICommandWithParameters` がサポートされている必要があります。  
  
 パラメーター情報は、このクラスによって作成および管理されるバッファーに格納されます。[GetParam](../Topic/CDynamicParameterAccessor::GetParam.md) と [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md) を使用してバッファーからパラメーター データを取得します。  
  
 このクラスを使用して SQL Server のストアド プロシージャを実行し、出力パラメーター値を取得する方法の例については、サポート技術情報の記事 Q058860 の「HOWTO: Execute Stored Procedure using CDynamicParameterAccessor」を参照してください。 サポート技術情報の記事は、MSDN ライブラリの Visual Studio マニュアルまたは [http:\/\/support.microsoft.com\/](http://support.microsoft.com) で参照できます。  
  
## 必要条件  
 **ヘッダー**: atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../Topic/CAccessor%20Class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CManualAccessor クラス](../Topic/CManualAccessor%20Class.md)