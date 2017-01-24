---
title: "ユーザー レコード | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクセサー [C++], 行セット"
  - "アクセサー [C++], static"
  - "BEGIN_ACCESSOR マクロ, 例"
  - "BEGIN_ACCESSOR_MAP マクロ"
  - "CAccessor クラス, 例"
  - "COLUMN_ENTRY マクロ"
  - "COLUMN_ENTRY_MAP マクロ"
  - "OLE DB コンシューマー テンプレート, ユーザー レコード"
  - "行セット [C++], アクセサー"
  - "ユーザー レコード, OLE DB コンシューマー テンプレート"
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ユーザー レコード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

静的アクセサー \(**CAccessor** から派生したアクセサー\) を使用するには、コンシューマーがユーザー レコードを保持している必要があります。  ユーザー レコードは、入力や出力を処理するためのデータ要素を含む C\+\+ クラスです。  ATL OLE DB コンシューマー ウィザードは、コンシューマーに対してユーザー レコードを生成します。  ユーザー レコードには、コマンドの処理などの省略可能なタスク用のメソッドを追加できます。  
  
 次のコードは、コマンドを処理するサンプル レコードです。  ユーザー レコードでは、`BEGIN_COLUMN_MAP` は、プロバイダーからコンシューマーに渡されるデータ行セットを表します。  `BEGIN_PARAM_MAP` は、一連のコマンド パラメーターを表します。  この例では、[CCommand](../../data/oledb/ccommand-class.md) クラスを使用してコマンド パラメーターを処理します。  マップ エントリのデータ メンバーは、1 つの連続するメモリ ブロック内でのクラスの各インスタンスのオフセットを表します。  `COLUMN_ENTRY` マクロは、プロバイダー側の `PROVIDER_COLUMN_ENTRY` マクロに対応します。  
  
 **COLUMN\_MAP** マクロと **PARAM\_MAP** マクロの詳細については、「[OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)」を参照してください。  
  
```  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
  
// Parameter binding map  
BEGIN_PARAM_MAP(CArtists)  
   COLUMN_ENTRY(1, m_nAge)  
END_PARAM_MAP()  
};  
```  
  
## ウィザード生成ユーザー レコード  
 ATL OLE DB コンシューマー ウィザードでコンシューマーを生成する場合は、OLE DB テンプレートまたは OLE DB 属性を使用できます。  どちらを使用するかによって、生成されるコードが異なります。  このコードの詳細については、「[コンシューマー ウィザードで生成されたクラス](../../data/oledb/consumer-wizard-generated-classes.md)」を参照してください。  
  
## ユーザー レコードによる複数のアクセサーのサポート  
 複数のアクセサーを使用する必要がある場合の詳細については、「[行セットでの複数アクセサーの使用](../Topic/Using%20Multiple%20Accessors%20on%20a%20Rowset.md)」を参照してください。  
  
 次の例は、行セットに対して複数のアクセサーをサポートするように変更されたユーザー レコードを示しています。  `BEGIN_COLUMN_MAP` と `END_COLUMN_MAP` の代わりに、各アクセサーに対して [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md) と [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) を使用しています。  `BEGIN_ACCESSOR` マクロは、アクセサー番号 \(0 からのオフセット\) と、アクセサーが自動アクセサーかどうかを指定します。  自動アクセサーは、[MoveNext](../../data/oledb/crowset-movenext.md) が呼び出されると、`GetData` を呼び出してデータを自動的に取得します。  非自動アクセサーでは、データを明示的に取得する必要があります。  非自動アクセサーは、ビットマップ イメージのような、すべてのレコードに対して取得する必要のない大きなデータ フィールドとバインドする場合に使用します。  
  
```  
class CMultiArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)  
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor  
    COLUMN_ENTRY(1, m_szFirstName)  
    COLUMN_ENTRY(2, m_szLastName)  
   END_ACCESSOR()  
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor  
    COLUMN_ENTRY(3, m_nAge)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)