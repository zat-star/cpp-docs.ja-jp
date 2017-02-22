---
title: "OLE DB 準拠合致テスト | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "準拠合致テスト"
  - "準拠合致テスト [OLE DB]"
  - "OLE DB プロバイダー, テスト"
  - "テスト (プロバイダーを)"
  - "テスト, OLE DB プロバイダー"
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE DB 準拠合致テスト
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダーに一貫性を持たせるために、Data Access SDK には OLE DB 準拠合致テストのセットが用意されています。  このテストは、プロバイダーのすべての機能を調べて、プロバイダーが予測どおりに機能するかどうかを検証するためのテストです。  OLE DB 準拠合致テストは、Microsoft Data Access SDK にあります。  ここでは、準拠合致テストに合格するために行う事柄について説明します。  OLE DB 準拠合致テストの実行については、SDK を参照してください。  
  
## 準拠合致テストの実行  
 Visual C\+\+ 6.0 では、OLE DB プロバイダー テンプレートで、値とプロパティを確認するための多数のフック関数が追加されました。  これらの関数のほとんどは、準拠合致テストに対応するために追加されました。  
  
> [!NOTE]
>  プロバイダーが OLE DB 準拠合致テストに合格するには、いくつかの検証関数を追加する必要があります。  
  
 このプロバイダーは、2 つの検証ルーチンを必要とします。  最初のルーチンである `CRowsetImpl::ValidateCommandID` は、行セット クラスの一部です。  これは、プロバイダー テンプレートによって行セットの作成時に呼び出されます。  サンプルは、このルーチンを使用して、インデックスをサポートしないことをコンシューマーに通知します。  最初の呼び出しは `CRowsetImpl::ValidateCommandID` に対するものです。プロバイダーは、「[プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)」で `CMyProviderRowset` のインターフェイス マップに追加された **\_RowsetBaseClass** typedef を使用するため、長いテンプレート引数を渡す必要はありません。  次に、インデックス パラメーターが **NULL** でない場合 \(コンシューマーがインデックスを使用することを示します\) は **DB\_E\_NOINDEX** を返します。  コマンド ID の詳細については、OLE DB 仕様で **IOpenRowset::OpenRowset** を検索してください。  
  
 次のコードは、**ValidateCommandID** 検証ルーチンです。  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
// Class: CMyProviderRowset   
  
HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)  
{  
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);  
   if (hr != S_OK)  
      return hr;  
  
   if (pIndexID != NULL)  
      return DB_E_NOINDEX;    // Doesn't support indexes  
  
   return S_OK;  
}  
```  
  
 プロバイダー テンプレートは、**DBPROPSET\_ROWSET** グループのプロパティが変更されるたびに、`OnPropertyChanged` メソッドを呼び出します。  他のグループのプロパティを扱う場合は、そのプロパティを適切なオブジェクトに追加します。この例では、**DBPROPSET\_SESSION** チェックは `CMyProviderSession` クラスに追加します。  
  
 コードは、最初に、プロパティが別のプロパティにリンクされているかどうかを調べます。  プロパティがチェーンされている場合は、**DBPROP\_BOOKMARKS** プロパティが True に設定されます。  OLE DB 仕様の付録 C には、プロパティに関する情報が記載されています。  この情報では、プロパティが別のプロパティにチェーンされているかどうかも示します。  
  
 また、`IsValidValue` ルーチンをコードに追加する場合もあります。  テンプレートはプロパティの設定を行う前に `IsValidValue` を呼び出します。  プロパティ値を設定するときに追加の処理が必要な場合は、このメソッドをオーバーライドします。  プロパティ セットごとに、これらのメソッドを 1 つ持つことができます。  
  
## スレッド処理の問題  
 既定では、ATL OLE DB プロバイダー ウィザードの OLE DB プロバイダー ウィザードは、アパートメント モデルで実行するプロバイダーのコードを生成します。  このコードを準拠合致テストで実行すると、最初は失敗します。  この原因は、OLE DB 準拠合致テストの実行に使用されるツールである Ltm.exe が、既定でフリー スレッドになっているためです。  OLE DB プロバイダー ウィザードのコードは、パフォーマンスと使いやすさの向上のために、既定ではアパートメント スレッド モデルになります。  
  
 この問題を解決するには、LTM を変更するか、プロバイダーを変更します。  
  
#### アパートメント スレッド モードで実行するように LTM を変更するには  
  
1.  LTM メイン メニューの \[Tools\] をクリックし、次に **\[Options\]** をクリックします。  
  
2.  \[General\] タブで、スレッド モデルを \[Free Threaded\] から \[Apartment\] に変更します。  
  
 フリー スレッド モードで実行するようにプロバイダーを変更するには  
  
-   プロバイダー プロジェクトで、`CComSingleThreadModel` のすべてのインスタンスを検索し、`CComMultiThreadModel` に置き換えます。これは、データ ソース、セッション、および行セット ヘッダー内にあります。  
  
-   .rgs ファイルでスレッド モデルを \[Apartment\] から \[Both\] に変更します。  
  
-   フリー スレッド プログラミングの適切なプログラミング規則 \(つまり、書き込み時のロック\) に従います。  
  
## 参照  
 [高度なプロバイダー手法](../Topic/Advanced%20Provider%20Techniques.md)