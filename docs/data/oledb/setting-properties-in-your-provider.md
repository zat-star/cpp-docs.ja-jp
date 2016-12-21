---
title: "プロバイダーでのプロパティの設定 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB プロバイダー, プロパティ"
  - "プロパティ [C++], OLE DB プロバイダー"
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロバイダーでのプロパティの設定
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

必要なプロパティのプロパティ グループとプロパティ ID を検索します。  詳細については、『OLE DB Programmer's Reference』の「[OLE DB Properties](https://msdn.microsoft.com/en-us/library/ms722734.aspx)」を参照してください。  
  
 ウィザードで生成されたプロバイダー コードで、プロパティ グループに対応するプロパティ マップを検索します。  通常、プロパティ グループの名前はオブジェクト名に対応します。  コマンドと行セットのプロパティは、コマンドまたは行セットにあります。データ ソースと初期化のプロパティは、データ ソース オブジェクトにあります。  
  
 プロパティ マップで、[PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md) マクロを追加します。  PROPERTY\_INFO\_ENTRY\_EX は、4 つのパラメーターを持ちます。  
  
-   プロパティのプロパティ ID。  プロパティ名から最初の 7 文字 \("DBPROP\_"\) を削除する必要があります。  たとえば、**DBPROP\_MAXROWS** を追加する場合は、`MAXROWS` を最初の要素として渡します。  これがカスタム プロパティである場合は、GUID 名全体 \(`DBMYPROP_MYPROPERTY` など\) を渡します。  
  
-   プロパティのバリアント型 \(『OLE DB Programmer's Reference』の「[OLE DB Properties](https://msdn.microsoft.com/en-us/library/ms722734.aspx)」を参照\)。  データ型に対応する **VT\_** の型 \(`VT_BOOL` や `VT_I2` など\) を入力します。  
  
-   プロパティが読み取りおよび書き込み可能かどうかを示すフラグと、プロパティが属するグループ。  たとえば、次のコードは行セット グループに属する読み取り\/書き込みプロパティを示します。  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   プロパティの基本値。  これには、ブール型の **VARIANT\_FALSE** や整数型の 0 などがあります。  プロパティは、変更されない限りこの値を保持します。  
  
    > [!NOTE]
    >  一部のプロパティは、ブックマークや更新などの他のプロパティに接続またはチェーンされています。  このため、コンシューマーが 1 つのプロパティを true に設定すると、別のプロパティも設定される場合があります。  OLE DB プロバイダー テンプレートは、[CUtlProps::OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md) メソッドを通じてこれをサポートします。  
  
## Microsoft OLE DB プロバイダーが無視するプロパティ  
 Microsoft OLE DB プロバイダーは、以下の OLE DB プロパティを無視します。  
  
-   **DBPROP\_MAXROWS** は、読み取り専用プロバイダー \(DBPROP\_IRowsetChange と DBPROP\_IRowsetUpdate が false の場合\) に対してだけ動作します。それ以外の場合、このプロパティはサポートされません。  
  
-   **DBPROP\_MAXPENDINGROWS** は無視されます。プロバイダーは独自の制限値を指定します。  
  
-   **DBPROP\_MAXOPENROWS** は無視されます。プロバイダーは独自の制限値を指定します。  
  
-   **DBPROP\_CANHOLDROWS** は無視されます。プロバイダーは独自の制限値を指定します。  
  
## 参照  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)