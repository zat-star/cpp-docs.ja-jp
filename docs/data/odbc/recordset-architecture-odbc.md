---
title: "レコードセット: レコードセットの構造 (ODBC) | Microsoft Docs"
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
  - "フィールド データ メンバー"
  - "フィールド データ メンバー, レコードセット アーキテクチャ"
  - "m_nFields データ メンバー"
  - "m_nFields データ メンバー, レコードセット"
  - "m_nParams データ メンバー"
  - "m_nParams データ メンバー, レコードセット"
  - "ODBC レコードセット, アーキテクチャ"
  - "パラメーター データ メンバー (レコードセットの内の)"
  - "レコードセット, アーキテクチャ"
  - "レコードセット, データ メンバー"
ms.assetid: 47555ddb-11be-4b9e-9b9a-f2931764d298
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコードセット: レコードセットの構造 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、レコードセット オブジェクトのアーキテクチャを構成するデータ メンバーについて説明します。  
  
-   [フィールド データ メンバー](#_core_field_data_members)  
  
-   [パラメーター データ メンバー](#_core_parameter_data_members)  
  
-   [m\_nFields と m\_nParams の利用法](#_core_using_m_nfields_and_m_nparams)  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。  バルク行フェッチが実装されているレコードセットの構造も基本的に同じです。  両者の差異については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
##  <a name="_core_a_sample_class"></a> クラスのサンプル  
 クラスの追加ウィザードの [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md) を使って `CRecordset` からの派生レコードセット クラスを宣言すると、次のような汎用構造のクラスが作成されます。  
  
```  
class CCourse : public CRecordset  
{  
public:  
   CCourse(CDatabase* pDatabase = NULL);  
   ...  
   CString m_strCourseID;  
   CString m_strCourseTitle;  
   CString m_strIDParam;  
};  
```  
  
 クラスの先頭には、一連の[フィールド データ メンバー](#_core_field_data_members)がウィザードによって記述されます。  クラスを作成するときは、1 つ以上のフィールド データ メンバーを指定する必要があります。  データ メンバー `m_strIDParam` を持つサンプル クラスのように、クラスをパラメーター化したときは、[パラメーター データ メンバー](#_core_parameter_data_members)を直接追加する必要があります。  ウィザードでクラスにパラメーターを追加することはできません。  
  
##  <a name="_core_field_data_members"></a> フィールド データ メンバー  
 レコードセット クラスで最も重要なメンバーは、フィールド データ メンバーです。  データ ソースから選択した列ごとに、該当するデータ型のデータ メンバー変数がクラスに用意されます。  たとえば、上記の[クラスのサンプル](#_core_a_sample_class)では、2 つの `CString` 型のフィールド データ メンバーである `m_strCourseID` と `m_strCourseTitle` が宣言されています。  
  
 レコードセットが一連のレコードを選択すると、フレームワークは自動的に、現在のレコード \(**Open** 呼び出しの後は、先頭レコードが現在のレコードになります\) のすべての列をオブジェクトのフィールド データ メンバーに連結します。  つまり、各フィールド データ メンバーは、対応するレコード列の内容を保存するためのバッファーとして使用されます。  
  
 ユーザーがスクロール操作によって新しいレコードに移動すると、フィールド データ メンバーは新しい現在のレコードを表すようになります。  フィールド データ メンバーに保存されていた、以前の現在のレコードの値はクリアされます。  フィールド データ メンバーは、現在のレコードの更新や新規レコードの追加にも使用されます。  レコード更新処理を行うときは、フィールド データ メンバーに値を直接代入して更新値を指定します。  
  
##  <a name="_core_parameter_data_members"></a> パラメーター データ メンバー  
 クラスをパラメーター化すると、クラスは 1 つ以上のパラメーター データ メンバーを持ちます。  パラメーター化されたクラスでは、実行時に取得した情報や計算で得た値に基づいてレコードセット クエリを作成できます。  
  
 通常は、次の例のように、パラメーターを使用して選択範囲を限定できます。  上記の[クラスのサンプル](#_core_a_sample_class)に基づいて作成したレコードセット オブジェクトは、次の SQL ステートメントを実行します。  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?  
```  
  
 上の例の "?" プレースホルダーには、実行時にパラメーター値が指定されます。  レコードセットを構築し、その `m_strIDParam` データ メンバーを MATH101 に設定すると、そのレコードセットに対して有効な SQL ステートメントは次のようになります。  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101  
```  
  
 SQL 文字列中のパラメーターの名前をフレームワークに対して通知するには、パラメーター データ メンバーを定義します。  フレームワークは、パラメーターを ODBC に結び付け、ODBC に対してプレースホルダー位置に挿入する値を取得する場所を知らせます。  この例では、クエリ実行後のレコードセットには、Course テーブルから CourseID 列の値が MATH101 であるレコードだけが格納されます。  このレコードの、指定されたすべての列が選択されます。  パラメーター \(とクエリの "?" プレースホルダー\) は、必要な数だけ指定できます。  
  
> [!NOTE]
>  MFC 自体は、パラメーターについては特に何もしません。具体的には、テキストも置き換えません。  代わりに、パラメーターを取得する場所を ODBC に伝えます。ODBC は、データを得て、必要なパラメーター化を実行します。  
  
> [!NOTE]
>  パラメーターの順序は重要です。  パラメーターの順序とパラメーターの詳細については、「[レコードセット : パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。  
  
##  <a name="_core_using_m_nfields_and_m_nparams"></a> m\_nFields と m\_nParams の利用法  
 ウィザードは、レコードセット クラスのコンストラクターを作成し、データ メンバー [m\_nFields](../Topic/CRecordset::m_nFields.md) の初期化コードを生成します。m\_nFields は、クラスの[フィールド データ メンバー](#_core_field_data_members)の総数を表す変数です。  [パラメーター](#_core_parameter_data_members)をクラスに追加した場合は、[m\_nParams](../Topic/CRecordset::m_nParams.md) データ メンバーの初期化コードも追加する必要があります。この m\_nParams データ メンバーを使用して、パラメーター データ メンバーの数を指定します。  フレームワークは、これらの値を使用してデータ メンバーを操作します。  
  
 詳細と例については、「[レコード フィールド エクスチェンジ : RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)」を参照してください。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: テーブルにアクセスするレコードセット クラスの宣言 \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [レコード フィールド エクスチェンジ \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)