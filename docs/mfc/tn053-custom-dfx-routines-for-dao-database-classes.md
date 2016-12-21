---
title: "テクニカル ノート 53: DAO データベース クラス用カスタム DFX ルーチン | Microsoft Docs"
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
  - "vc.mfc.dfx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "カスタム DFX ルーチン [C++]"
  - "DAO [C++], クラス"
  - "DAO [C++], MFC"
  - "データベース クラス [C++], DAO"
  - "DFX (DAO レコード フィールド エクスチェンジ) [C++]"
  - "DFX (DAO レコード フィールド エクスチェンジ) [C++], カスタム ルーチン"
  - "MFC [C++], DAO および"
  - "TN053"
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 53: DAO データベース クラス用カスタム DFX ルーチン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Visual C\+\+ .NET では、Visual C\+\+ 開発環境およびウィザードでは DAO はサポートされなくなりました \(DAO クラスは含まれているので、このクラスを使うことはできます\)。  Microsoft は、新しいプロジェクトに [OLE DB テンプレート](../Topic/OLE%20DB%20Templates.md) または [ODBC と MFC](../data/odbc/odbc-and-mfc.md) を使用することをお勧めします。  DAO は、既存のアプリケーションを保守するためだけに使用してください。  
  
 このテクニカル ノートは DAO レコード フィールド エクスチェンジ \(RFX\) 関数の機能について説明します。  DFX ルーチンで実行されていることを理解しやすいように、`DFX_Text` 関数は例として詳しく説明します。  このテクニカル ノートに追加情報源として、ユーザー DFX 関数他のコードを調べることができます。  カスタム RFX ルーチンを可能性があるほど、カスタム DFX ルーチンを頻繁に必要としません \(ODBC データベース クラスで使用される\) が必要です。  
  
 このテクニカル ノートは含まれています:  
  
-   DFX の概要  
  
-   DAO レコード フィールド エクスチェンジと動的バインディングを使用して[例](#_mfcnotes_tn053_examples)  
  
-   [DFX のしくみについて](#_mfcnotes_tn053_how_dfx_works)  
  
-   [カスタム DFX ルーチンが何を](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)  
  
-   [DFX\_Text の詳細](#_mfcnotes_tn053_details_of_dfx_text)  
  
 **DFX の概要**  
  
 `CDaoRecordset` クラスを使用すると DAO レコード フィールド エクスチェンジ \(RFX\) 関数の機能がデータを取得すると更新する手順を簡素化するために使用されます。  プロセスは `CDaoRecordset` クラスのデータ メンバーを使用して簡略化されます。  `CDaoRecordset`から派生して、テーブルまたはクエリの各フィールドを表す派生クラスにデータ メンバーを追加できます。  この「静的バインディング」機構は単純ですが、すべてのアプリケーションに対して選択したデータ フェッチ\/更新メソッドではない可能性があります。  DFX は現在のレコードが変更されるたびに、バインドされたフィールドを取得します。  通貨が変更されたときに、フィールドをフェッチする必要なくパフォーマンス センシティブ アプリケーションを開発する場合、`CDaoRecordset::GetFieldValue` して「動的バインディング」と `CDaoRecordset::SetFieldValue` はデータ アクセスの選択モードである場合があります。  
  
> [!NOTE]
>  DFX と動的バインディングは同時に指定できなくないです。したがって、静的リソース参照と動的バインディングを組み合わせた使用を使用できます。  
  
 **例 DAO レコード フィールド エクスチェンジのみの使用**  
  
 \(`CDaoRecordset` —開く派生クラス `CMySet` "を既に仮定します\)  
  
```  
// Add a new record to the customers table  
myset.AddNew();  
myset.m_strCustID = _T("MSFT");  
myset.m_strCustName = _T("Microsoft");  
myset.Update();  
```  
  
 **例 2 \- 動的バインディングのみの使用**  
  
 \(`CDaoRecordset` クラス、`rs`を使用していて、既に開かれています\)  
  
```  
// Add a new record to the customers table  
COleVariant  varFieldValue1 ( _T("MSFT"), VT_BSTRT );  
//Note: VT_BSTRT flags string type as ANSI, instead of UNICODE default  
COleVariant  varFieldValue2  (_T("Microsoft"), VT_BSTRT );  
rs.AddNew();  
rs.SetFieldValue(_T("Customer_ID"), varFieldValue1);  
rs.SetFieldValue(_T("Customer_Name"), varFieldValue2);  
rs.Update();  
```  
  
 **例 DAO レコード フィールド エクスチェンジと動的バインディングの使用**  
  
 \(`CDaoRecordset`の参照の従業員データ\-派生クラス `emp`を仮定します\)  
  
```  
// Get the employee's data so that it can be displayed  
emp.MoveNext();  
  
// If user wants to see employee's photograph,  
// fetch it  
COleVariant varPhoto;  
if (bSeePicture)  
   emp.GetFieldValue(_T("photo"), varPhoto);  
  
// Display the data  
PopUpEmployeeData(emp.m_strFirstName,  
    emp.m_strLastName, varPhoto);  
```  
  
 **DFX のしくみについて**  
  
 DFX の機能は、MFC ODBC クラスによって使用されるレコード フィールド エクスチェンジ \(RFX\) の機能と同様に機能します。  RFX と DFX の原則は同じですが、多数の内部違いがあります。  DFX 関数のデザインは、すべてのコードがユーザー DFX ルーチンによって共有されるようになりました。  最上位 DFX でさまざまな項目のみを表示します。  
  
-   DFX は SQL **SELECT** 句および SQL **PARAMETERS** 句を必要に応じて構築します。  
  
-   DFX は DAO の `GetRows` 関数 \(の後にこれ以上\) で使用される結合の構造を構築します。  
  
-   DFX \(ダブル バッファリングを使用する場合\) が変更されたフィールドを検出するために使用されるデータ バッファーを管理します。  
  
-   DFX は更新の **NULL** と **DIRTY** 状態の配列と設定値を必要に応じて管理します。  
  
 DFX の機能の中核となるの `CDaoRecordset` の派生クラスの `DoFieldExchange` 関数です。  この関数は、適切な型のユーザー操作の DFX の関数呼び出しをディスパッチします。  `DoFieldExchange` を内部 MFC 関数を呼び出す前に操作の種類を設定します。  次のリストは、さまざまなアクションの種類と簡単な説明が表示されます。  
  
|操作|説明|  
|--------|--------|  
|**AddToParameterList**|ビルド パラメーター句|  
|**AddToSelectList**|ビルドは句を選択します。|  
|**BindField**|結合の構造を設定します。|  
|**BindParam**|パラメーター値を設定します。|  
|**Fixup**|設定の空白の状態|  
|**AllocCache**|ダーティ チェックのキャッシュを割り当てます。|  
|**StoreField**|現在のレコードをキャッシュに保存します。|  
|**LoadField**|復元がメンバー値をキャッシュ|  
|**FreeCache**|キャッシュを解放します。|  
|`SetFieldNull`|フィールド ステータス値を & null に設定します。|  
|**MarkForAddNew**|変更されたフィールドを受け入れない場合 PSEUDO NULL マークします。|  
|**MarkForEdit**|キャッシュと一致しない場合は変更されたフィールドをマークします。|  
|**SetDirtyField**|フィールドの値が変更されたことを示すマークを設定します。|  
  
 次のセクションでは、各アクションは `DFX_Text`について詳しく説明します。  
  
 DAO レコード フィールド エクスチェンジ プロセスについて理解する最も重要な機能は `CDaoRecordset` オブジェクトの `GetRows` 関数を使用します。  DAO `GetRows` 関数が複数の方法で使用できます。  このテクニカル ノートは簡単にこのテクニカル ノートのスコープ外にある場合にのみ `GetRows` について説明します。  
  
 DAO `GetRows` は複数の方法で使用できます。  
  
-   これは、複数のデータ レコードと複数のフィールドを一度にフェッチできます。  これは、大規模なデータ構造を処理することで、より高速なデータ アクセスと各フィールドに適切なオフセットと構造体の各データ レコードを有効にします。  MFC はこの機能をフェッチする複数のレコードを使用しません。  
  
-   `GetRows` が操作するもう一つの方法は、1 種類のデータ レコードの各フィールドを取得したデータのバインド アドレスを指定することをプログラマが持つことです。  
  
-   DAO は、可変長の列の呼び出し元を「コールバック」呼び出し元がメモリを割り当てることができます。  2 番目の機能に `CDaoRecordset` クラス \(派生クラス\) のメンバーにデータの部数を最小限に抑えるため、データを直接ストレージを使用することの利点があります。  2 番目の機能は `CDaoRecordset` の派生クラスのデータ メンバーにバインドする MFC メソッドの使用です。  
  
##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> カスタム DFX ルーチンが何を  
 、DFX 関数で実装される正常に `GetRows`を呼び出すための最も重要な操作が必要なデータ構造を設定する機能である必要があります。この説明では顕著です。  他のいくつかの操作 DFX 関数と同様にサポートする必要があること `GetRows` の呼び出しで正しく準備する重要または複雑な None 同様に。  
  
 DFX を使用すると、オンライン ドキュメントで説明されています。  基本的に、2 個の要件があります。  最初に、メンバーは、バインドされたフィールドとパラメーターの `CDaoRecordset` の派生クラスに追加する必要があります。  この `CDaoRecordset::DoFieldExchange` の後でオーバーライドする必要があります。  メンバーのデータ型が重要であることに注意してください。  これは、データベースのフィールドのデータに一致するか、またはその型に変換可能な一つ以上のようになります。  データベースなどの数値フィールドは、長整数などの `CString` のメンバーにテキストを送信し、境界は、常に変換できるデータベースのテキスト フィールドです長整数のメンバーへの長整数および境界などの数値表現には、変換されていない可能性があります。   \(MFC\) ではなく、DAO の Microsoft Jet データベース エンジンが変換を行います。  
  
##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a> DFX\_Text の詳細  
 前述のとおり、DFX 作業を例に対する操作方法を説明する最善の方法。  このため `DFX_Text` の内部に移動と DFX の少なくとも基礎的な機能を提供するためのさまざまな効果的な必要があります。  
  
 **AddToParameterList**  
 この操作は、Jet に必要な SQL **PARAMETERS** 句 \(「`Parameters <param name>, <param type> ... ;`」\) をビルドします。  各パラメーターには名前があり、入力されます \(RFX 関数呼び出しで指定されている\)。  個々の型名を参照するように関数の **CDaoFieldExchange::AppendParamType** 関数を参照してください。  `DFX_Text`の場合、使用する型が `text`です。  
  
 **AddToSelectList**  
 SQL **SELECT** 句を作成します。  これは DFX の呼び出しで指定された項目の名前が単に付けられているため、非常に単純です \(「`SELECT <column name>, ...`」\)。  
  
 **BindField**  
 操作の最も複雑です。  前に述べたように、これ `GetRows` で使われる DAO の結合の構造が設定されている場所です。  `DFX_Text` のコードから参照できるように、構造体の情報の種類に使われる DAO の型が表示されます。`DFX_Text`の場合は**DAO\_CHAR** または **DAO\_WCHAR**\)。  また、使用されるバインディングの種類はセットアップされます。  前のセクションで `GetRows` が一時的にのみ説明していますが、MFC で使用するバインディングの種類が直接アドレス バインディング \(常に**DAOBINDING\_DIRECT**\) であることを示すだけです。  また、可変長の列のバインディング \(`DFX_Text`など\) をコールバックのバインディングに MFC でメモリの割り当てを制御し、適切な長さのアドレスを指定するために使用されます。  これがデータを格納するような意味は、MFC DAO を「常に指示できます。位置に」で直接メンバー変数へのバインドを許可します。  結合の構造の残りの部分には、列バインディングのメモリ割り当てにコールバック関数と型のアドレスなどが格納されます \(項目の名前によってバインドする\)。  
  
 **BindParam**  
 つまり、パラメーター メンバーに指定されるパラメーター値を使用して `SetParamValue` を呼び出す単純な操作です。  
  
 **Fixup**  
 各フィールドの **NULL** の状態を設定します。  
  
 `SetFieldNull`  
 この操作は **NULL** としてのみ各フィールド ステータスを示し、**PSEUDO\_NULL**にメンバー変数の値を設定します。  
  
 **SetDirtyField**  
 各フィールドに指定されたダーティの `SetFieldValue` を呼び出します。  
  
 残りのすべての操作がデータ キャッシュの使用だけが処理されます。  データ キャッシュは特定の操作を簡単にするために使用する、現在のレコードの追加バッファーです。  たとえば、「ダーティ」フィールドは自動的に検出できます。  オンライン ドキュメントで説明されているように、これは完全にフィールドまたはレベルでオフにできます。  バッファーの実装、マップを使用します。  このマップの「バインドされた」フィールドのアドレスとデータの動的に割り当てられたコピー使用されます \(または `CDaoRecordset` をデータ メンバーを派生しました\) 調和させるために使用されます。  
  
 **AllocCache**  
 動的にキャッシュ フィールドに値を割り当てたり、マップに追加します。  
  
 **FreeCache**  
 キャッシュ フィールド値を削除し、マップから削除します。  
  
 **StoreField**  
 データ キャッシュに現在のフィールドの値をコピーします。  
  
 **LoadField**  
 フィールド メンバーにキャッシュされた値をコピーします。  
  
 **MarkForAddNew**  
 現在のフィールドの値が、**NULL** および必要に応じてマーク、ダーティかどうかを確認します。  
  
 **MarkForEdit**  
 データ キャッシュに、現在のフィールドの値が変更されたとマークを必要に応じて比較します。  
  
> [!TIP]
>  基本データ型の既存の DFX ルーチンのカスタム DFX ルーチンをシミュレートします。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)