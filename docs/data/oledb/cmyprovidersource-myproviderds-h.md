---
title: "CMyProviderSource (MyProviderDS.H) | Microsoft Docs"
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
  - ""myproviderds.h""
  - "cmyprovidersource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderSource クラス MyProviderDS.H"
  - "OLE DB プロバイダー, ウィザードが生成したファイル"
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSource (MyProviderDS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダー クラスは複数の継承を使用します。  次に示すコードは、データ ソース オブジェクトの継承チェインです。  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSource  
class ATL_NO_VTABLE CMyProviderSource :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public CComCoClass<CMyProviderSource, &CLSID_MyProvider>,  
   public IDBCreateSessionImpl<CMyProviderSource, CMyProviderSession>,  
   public IDBInitializeImpl<CMyProviderSource>,  
   public IDBPropertiesImpl<CMyProviderSource>,  
   public IPersistImpl<CMyProviderSource>,  
   public IInternalConnectionImpl<CMyProviderSource>  
```  
  
 すべての COM コンポーネントは、`CComObjectRootEx` および `CComCoClass` から派生します。  `CComObjectRootEx` は、すべての **IUnknown** インターフェイスの実装を提供します。  これは、すべてのスレッド モデルを処理することができます。  `CComCoClass` は、必要なエラー サポートを処理します。  クライアントに送るエラー情報をより充実した内容にする場合は、`CComCoClass` に含まれるエラー API のいくつかを使用できます。  
  
 このデータ ソース オブジェクトは、いくつかの "Impl" クラス \(名前が "Impl" で終わるクラス\) からも継承を行います。  これらの Impl クラスはいずれもインターフェイスのための実装を提供します。  データ ソース オブジェクトは、`IPersist`、`IDBProperties`、**IDBInitialize**、および **IDBCreateSession** の 4 つのインターフェイスを実装します。  これらのインターフェイスはいずれも、OLE DB がデータ ソース オブジェクトを実装するのに必要です。  これらの Impl クラスのどれを継承するかによって、特定の機能をサポートするかどうかを選択できます。  **IDBDataSourceAdmin** インターフェイスをサポートする場合は、**IDBDataSourceAdminImpl** クラスから継承することで、必要な機能を取得できます。  
  
## COM マップ  
 クライアントは、データ ソースのインターフェイスに対して `QueryInterface` を呼び出すときに、次の COM マップを調べます。  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 COM\_INTERFACE\_ENTRY マクロは ATL のマクロであり、`CComObjectRootEx` 内の `QueryInterface` の実装に適切なインターフェイスを返すよう指示します。  
  
## プロパティ マップ  
 プロパティ マップは、プロバイダーにより指定されたすべてのプロパティを指定します。  
  
```  
BEGIN_PROPSET_MAP(CMyProviderSource)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
      PROPERTY_INFO_ENTRY(ACTIVESESSIONS)  
      PROPERTY_INFO_ENTRY(ASYNCTXNABORT)  
      PROPERTY_INFO_ENTRY(ASYNCTXNCOMMIT)  
      PROPERTY_INFO_ENTRY(BYREFACCESSORS)  
      PROPERTY_INFO_ENTRY_VALUE(CATALOGLOCATION, DBPROPVAL_CL_START)  
      PROPERTY_INFO_ENTRY(CATALOGTERM)  
      PROPERTY_INFO_ENTRY(CATALOGUSAGE)  
      PROPERTY_INFO_ENTRY(COLUMNDEFINITION)  
      PROPERTY_INFO_ENTRY(CONCATNULLBEHAVIOR)  
      PROPERTY_INFO_ENTRY(DATASOURCENAME)  
      PROPERTY_INFO_ENTRY(DATASOURCEREADONLY)  
      PROPERTY_INFO_ENTRY(DBMSNAME)  
      PROPERTY_INFO_ENTRY(DBMSVER)  
      PROPERTY_INFO_ENTRY_VALUE(DSOTHREADMODEL, DBPROPVAL_RT_FREETHREAD)  
      PROPERTY_INFO_ENTRY(GROUPBY)  
      PROPERTY_INFO_ENTRY(HETEROGENEOUSTABLES)  
      PROPERTY_INFO_ENTRY(IDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(MAXINDEXSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZEINCLUDESBLOB)  
      PROPERTY_INFO_ENTRY(MAXTABLESINSELECT)  
      PROPERTY_INFO_ENTRY(MULTIPLEPARAMSETS)  
      PROPERTY_INFO_ENTRY(MULTIPLERESULTS)  
      PROPERTY_INFO_ENTRY(MULTIPLESTORAGEOBJECTS)  
      PROPERTY_INFO_ENTRY(MULTITABLEUPDATE)  
      PROPERTY_INFO_ENTRY(NULLCOLLATION)  
      PROPERTY_INFO_ENTRY(OLEOBJECTS)  
      PROPERTY_INFO_ENTRY(ORDERBYCOLUMNSINSELECT)  
      PROPERTY_INFO_ENTRY(OUTPUTPARAMETERAVAILABILITY)  
      PROPERTY_INFO_ENTRY(PERSISTENTIDTYPE)  
      PROPERTY_INFO_ENTRY(PREPAREABORTBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PREPARECOMMITBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PROCEDURETERM)  
      PROPERTY_INFO_ENTRY(PROVIDERNAME)  
      PROPERTY_INFO_ENTRY(PROVIDEROLEDBVER)  
      PROPERTY_INFO_ENTRY(PROVIDERVER)  
      PROPERTY_INFO_ENTRY(QUOTEDIDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(ROWSETCONVERSIONSONCOMMAND)  
      PROPERTY_INFO_ENTRY(SCHEMATERM)  
      PROPERTY_INFO_ENTRY(SCHEMAUSAGE)  
      PROPERTY_INFO_ENTRY(STRUCTUREDSTORAGE)  
      PROPERTY_INFO_ENTRY(SUBQUERIES)  
      PROPERTY_INFO_ENTRY(TABLETERM)  
      PROPERTY_INFO_ENTRY(USERNAME)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
   BEGIN_PROPERTY_SET(DBPROPSET_DBINIT)  
      PROPERTY_INFO_ENTRY(AUTH_PASSWORD)  
      PROPERTY_INFO_ENTRY(AUTH_PERSIST_SENSITIVE_AUTHINFO)  
      PROPERTY_INFO_ENTRY(AUTH_USERID)  
      PROPERTY_INFO_ENTRY(INIT_DATASOURCE)  
      PROPERTY_INFO_ENTRY(INIT_HWND)  
      PROPERTY_INFO_ENTRY(INIT_LCID)  
      PROPERTY_INFO_ENTRY(INIT_LOCATION)  
      PROPERTY_INFO_ENTRY(INIT_MODE)  
      PROPERTY_INFO_ENTRY(INIT_PROMPT)  
      PROPERTY_INFO_ENTRY(INIT_PROVIDERSTRING)  
      PROPERTY_INFO_ENTRY(INIT_TIMEOUT)  
   END_PROPERTY_SET(DBPROPSET_DBINIT)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCE)  
      PROPERTY_INFO_ENTRY(CURRENTCATALOG)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCE)  
   CHAIN_PROPERTY_SET(CMyProviderSession)  
END_PROPSET_MAP()  
```  
  
 OLE DB のプロパティはグループ化されます。  データ ソース オブジェクトには、2 つのプロパティ グループがあります。1 つは **DBPROPSET\_DATASOURCEINFO** セットに対するグループで、もう 1 つは **DBPROPSET\_DBINIT** セットに対するグループです。  **DBPROPSET\_DATASOURCEINFO** セットは、プロバイダーとそのデータ ソースに関するプロパティに対応します。  **DBPROPSET\_DBINIT** セットは、初期化時に使用されるプロパティに対応します。  OLE DB プロバイダー テンプレートは、これらのセットを PROPERTY\_SET マクロで処理します。  このマクロは、プロパティの配列を含むブロックを作成します。  クライアントが `IDBProperties` インターフェイスを呼び出すたびに、プロバイダーはプロパティ マップを使用します。  
  
 仕様にあるすべてのプロパティを実装する必要はありません。  ただし、必須プロパティはサポートする必要があります。詳細については、レベル 0 準拠の仕様を参照してください。  プロパティをサポートしない場合は、マップから削除できます。  プロパティをサポートする場合は、PROPERTY\_INFO\_ENTRY マクロを使用してマップに追加します。  マクロが対応する **UPROPINFO** 構造体を次に示します。  
  
```  
struct UPROPINFO  
{  
   DBPROPID    dwPropId;  
   ULONG       ulIDS;  
   VARTYPE     VarType;  
   DBPROPFLAGS dwFlags;  
   union  
   {  
      DWORD dwVal;  
      LPOLESTR szVal;  
   };  
   DBPROPOPTIONS dwOption;  
};  
```  
  
 構造体の各要素は、プロパティを処理するための情報を表します。  これには、プロパティの GUID と ID を決定する **DBPROPID** が含まれます。  また、プロパティの種類と値を決定するエントリも含まれます。  
  
 プロパティの既定値を変更する場合 \(コンシューマーは書き込み可能プロパティの値をいつでも変更できます\) は、PROPERTY\_INFO\_ENTRY\_VALUE マクロまたは PROPERTY\_INFO\_ENTRY\_EX マクロを使用できます。  これらのマクロでは、対応するプロパティの値を指定できます。  PROPERTY\_INFO\_ENTRY\_VALUE マクロは、プロパティの値をすばやく変更するための手段を提供します。  PROPERTY\_INFO\_ENTRY\_VALUE マクロは、PROPERTY\_INFO\_ENTRY\_EX マクロを呼び出します。  このマクロでは、**UPROPINFO** 構造体のすべての属性を追加または変更できます。  
  
 独自のプロパティ セットを定義すると、追加の BEGIN\_PROPSET\_MAP\/END\_PROPSET\_MAP の組み合わせを作成することにより、そのプロパティ セットを追加できます。  プロパティ セットの GUID を定義してから、独自のプロパティを定義する必要があります。  プロバイダー固有のプロパティがある場合は、既存のプロパティを使用する代わりに、それらを新規のプロパティ セットに追加します。  これにより、新しいバージョンの OLE DB での問題が回避されます。  
  
## ユーザー定義のプロパティ セット  
 Visual C\+\+ .NET は、ユーザー定義のプロパティ セットをサポートします。  **GetProperties** または `GetPropertyInfo` をオーバーライドする必要はなくなりました。  代わりに、テンプレートは任意のユーザー定義のプロパティ セットを検出し、適切なオブジェクトに追加します。  
  
 ユーザー定義のプロパティ セットを初期化時 \(つまり、コンシューマーが **IDBInitialize::Initialize** を呼び出す前\) に使用できるようにする必要がある場合は、**UPROPSET\_USERINIT** フラグを BEGIN\_PROPERTY\_SET\_EX マクロと組み合わせて使用します。  これには、OLE DB 仕様で要求されているようにプロパティ セットがデータ ソース オブジェクト内にある必要があります。  たとえば、次のようになります。  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## 参照  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)