---
title: "db_accessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_accessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_accessor attribute"
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_accessor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`IAccessor` のベースのバインディングに含める **db\_column** の属性をグループ化します。  
  
## 構文  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### パラメーター  
 *num*  
 アクセサーの番号 \(ベース\) の整数インデックスを指定します。  整数または定義済みの値を使用して昇順にアクセサーの番号を指定する必要があります。  
  
 *自動*  
 アクセサーが自動的に取得されます \(\)**True** 取得されていないかどうかを指定するブール値 \(**False**\)。  
  
## 解説  
 **db\_accessor** は後続の **db\_column** の根本的な OLE DB のアクセサーと同じクラスまたは関数内の **db\_param** の属性を定義します。  **db\_accessor** にはメンバー レベルで使用できOLE DB `IAccessor` のベースのバインディングに含める **db\_column** の属性をグループ化するために使用されます。  これは **db\_table** または **db\_command** 属性とともに使用されます。  この属性を呼び出す [BEGIN\_ACCESSOR](../data/oledb/begin-accessor.md) と [END\_ACCESSOR](../Topic/END_ACCESSOR.md) マクロの呼び出しに似ています。  
  
 **db\_accessor** は行セットが生成され対応するアクセサーのマップにバインドします。  **db\_accessor** を呼び出してアクセサー 0 は自動的に生成されすべての列バインディングはこのアクセサー ブロックにマップされます。  
  
 **db\_accessor** は一つ以上のアクセサーにはデータベース列連結をグループ化します。  ユーザーが複数のアクセサーを使用する必要があるシナリオの詳細については [行セットの複数のアクセサーを使用します](../Topic/Using%20Multiple%20Accessors%20on%20a%20Rowset.md) を参照してください。  「 [ユーザー レコード](../data/oledb/user-records.md) の複数のアクセサーのユーザー レコード サポート」を参照してください。  
  
 コンシューマー属性プロバイダーがクラスにこの属性を適用するとコンパイラは *YourClassName* はクラスを受け取るとコンパイラは\_YourClassNameAccessor から派生 *YourClassName と*  いうクラスを作成する名前です \_YourClassNameAccessor にクラスの名前を変更します。  \[クラス ビュー\] でこれらのクラスを参照してください。  
  
## 使用例  
 次の例では2 人のアクセサーに Northwind データベースからOrders テーブル内のグループの列に **db\_accessor** を使用します。  アクセサー 0 は自動アクセサーでありアクセサー 1 はありません。  
  
```  
// cpp_attr_ref_db_accessor.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include <atlbase.h>  
#include <atldbcli.h>  
  
[ db_command(L"SELECT LastName, FirstName FROM Orders") ]  
class CEmployees {  
public:  
   [ db_accessor(0, TRUE) ];  
   [ db_column("1") ] LONG m_OrderID;  
   [ db_column("2") ] TCHAR m_CustomerID[6];  
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;   
  
   [ db_accessor(1, FALSE) ];  
   [ db_column("8") ] CURRENCY m_Freight;  
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|属性ブロック|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)