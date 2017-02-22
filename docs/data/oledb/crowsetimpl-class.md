---
title: "CRowsetImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl"
  - "ATL.CRowsetImpl"
  - "ATL::CRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRowsetImpl クラス"
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CRowsetImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

多くのインターフェイス実装の多重継承を必要とせずに標準 OLE DB の行セットの実装を提供します。  
  
## 構文  
  
```  
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl < T, IRowset >   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
#### パラメーター  
 `T`  
 `CRowsetImpl`から派生するユーザーのクラス。  
  
 `Storage`  
 ユーザー レコード クラスです。  
  
 `CreatorClass`  
 行セットのプロパティを含むクラス; 通常、コマンド。  
  
 `ArrayType`  
 行セットのデータの記憶領域として機能するクラス。  パラメーターの既定 `CAtlArray`にこの、が、必要な機能をサポートする任意のクラスを指定できます。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[NameFromDBID](../../data/oledb/crowsetimpl-namefromdbid.md)|渡された `bstr` に **DBID** とコピーから文字列を格納します。|  
|[SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)|2 桁の文字列に **DBID**s を検証し、保存します。[m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) と [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)\)。|  
  
### オーバーライド可能なメソッド  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/crowsetimpl-getcolumninfo.md)|特定のクライアント要求の列情報を取得します。|  
|[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)|その場合は、いずれか一方または両方のパラメーターがデータ メンバー [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) と [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)に文字列値をコピー文字列値に含まれている参照するかどうかを調べます。|  
|[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)|一方または両方の **DBID**s がある場合、文字列値が含まれている場合、参照するかどうかは、データ メンバー [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) と [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)にコピーします。|  
  
### データ メンバー  
  
|||  
|-|-|  
|[m\_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)|`CRowsetImpl`にユーザー レコード テンプレート引数で templatizes 既定で、`CAtlArray`。  別の配列型クラスの `CRowsetImpl`へ `ArrayType` テンプレート引数を変更することで実行できます。|  
|[m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)|行セットの最初のコマンドが含まれています。|  
|[m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)|行セットの最初のインデックスが含まれています。|  
  
## 解説  
 `CRowsetImpl` は 静的なアップキャスト形式のオーバーライドが含まれています。  メソッドは特定の行セットのコマンド テキストを検証する方法を制御します。  多重継承されるインターフェイス実装を作成して `CRowsetImpl`独自の式のクラスを作成できます。  、実装を提供する必要があるのは **実行**メソッドです。  どのようなによって行セットが作成されるか、作成者のメソッドは **実行**ごとに異なるシグネチャを要求します。  たとえば、実装する必要 `CRowsetImpl`\-派生クラス\) を使用している場合は、スキーマ行セットに、**実行** の次のメソッド シグネチャがあります:  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 実装する必要 `CRowsetImpl`\-派生クラス\) を作成するコマンドまたはセッションの行セットに、**実行** の次のメソッド シグネチャがあります:  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 `CRowsetImpl`を実装するための **実行** \-派生のメソッド、内部データ バッファー \([m\_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)\) を設定しなければなりません。  
  
## 必要条件  
 **ヘッダー:** atldb.h