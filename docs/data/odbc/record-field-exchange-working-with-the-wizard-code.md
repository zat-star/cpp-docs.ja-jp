---
title: "レコード フィールド エクスチェンジ: ウィザード コードの操作 | Microsoft Docs"
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
  - "DoFieldExchange メソッド, オーバーライド"
  - "フィールド データ メンバー"
  - "フィールド データ メンバー, 宣言"
  - "m_nFields データ メンバー"
  - "m_nFields データ メンバー, 初期化"
  - "m_nParams データ メンバー"
  - "m_nParams データ メンバー, 初期化"
  - "ODBC, RFX"
  - "オーバーライド, DoFieldExchange"
  - "RFX (ODBC), 実装"
  - "RFX (ODBC), ウィザード コード"
  - "Unicode, データベース クラスを使用する"
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコード フィールド エクスチェンジ: ウィザード コードの操作
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、MFC のアプリケーション ウィザードとクラスの追加 \(「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照\) で RFX をサポートするために生成するコードと、そのコードの変更方法について説明します。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生クラスを対象にしています。  バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ \(Bulk RFX: Bulk Record Field Exchange\) が実装されています。  Bulk RFX と RFX は似ています。  両者の差異については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 MFC のアプリケーション ウィザードやクラスの追加を使ってレコードセット クラスを作成すると、選択したデータ ソース、テーブル、および列に応じて、以下の RFX 関連コードが生成されます。  
  
-   レコードセット フィールド データ メンバーの宣言 \(レコードセット クラス宣言部\)  
  
-   `CRecordset::DoFieldExchange` オーバーライド関数  
  
-   レコードセット クラスのコンストラクターでのレコードセット フィールド データ メンバーの初期化。  
  
##  <a name="_core_the_field_data_member_declarations"></a> フィールド データ メンバーの宣言  
 ウィザードは、.h ファイルにレコードセット クラスの宣言コードを生成します。`CSections` クラスの宣言の例を次に示します。  
  
```  
class CSections : public CRecordset  
{  
public:  
   CSections(CDatabase* pDatabase = NULL);  
   DECLARE_DYNAMIC(CSections)  
  
// Field/Param Data  
   CString   m_strCourseID;  
   CString   m_strInstructorID;  
   CString   m_strRoomNo;  
   CString   m_strSchedule;  
   CString   m_strSectionNo;  
  
// Overrides  
   // Wizard generated virtual function overrides  
   protected:  
   virtual CString GetDefaultConnect();  // Default connection string  
   virtual CString GetDefaultSQL();      // Default SQL for Recordset  
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support  
  
// Implementation  
#ifdef _DEBUG  
   virtual void AssertValid() const;  
   virtual void Dump(CDumpContext& dc) const;  
#endif  
  
};  
```  
  
 パラメーター データ メンバー、または自分で結び付ける新しいフィールド データ メンバーを追加する場合は、ウィザードが生成したコードの後に追加します。  
  
 `CRecordset` クラスのメンバー関数 `DoFieldExchange` は、ウィザードによってオーバーライドされます。  
  
##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange オーバーライド関数  
 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) 関数は、RFX の中核です。  フレームワークは、データ ソースとレコードセットの間でデータの移動が必要になると、`DoFieldExchange` を呼び出します。  また、`DoFieldExchange` は、[IsFieldDirty](../Topic/CRecordset::IsFieldDirty.md) メンバー関数および [IsFieldNull](../Topic/CRecordset::IsFieldNull.md) メンバー関数を使用して、フィールド データ メンバーに関する情報を取得することもできます。  
  
 次の例は、`CSections` クラスで関数 `DoFieldExchange` をオーバーライドしている部分です。  ウィザードは、レコードセット クラスの .cpp ファイルにこの関数を作成します。  
  
```  
void CSections::DoFieldExchange(CFieldExchange* pFX)  
{  
   pFX->SetFieldType(CFieldExchange::outputColumn);  
   RFX_Text(pFX, "CourseID", m_strCourseID);  
   RFX_Text(pFX, "InstructorID", m_strInstructorID);  
   RFX_Text(pFX, "RoomNo", m_strRoomNo);  
   RFX_Text(pFX, "Schedule", m_strSchedule);  
   RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 この関数には以下の特徴があります。  
  
-   関数のこのセクションをフィールド マップと呼びます。  
  
-   `pFX` ポインターを通じて `CFieldExchange::SetFieldType` が呼び出されます。  この呼び出しによって、`DoFieldExchange` の終わりまでの RFX 関数呼び出しまたは `SetFieldType` に対する次の呼び出しを出力列に指定します。  詳細については、「[CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md)」を参照してください。  
  
-   フィールド データ メンバー \(上の例ではすべて `CString` 型変数\) ごとに、`RFX_Text` グローバル関数が呼び出されます。  この呼び出しによって、データ ソース中の列名とフィールド データ メンバー間の関係を指定します。  これらの RFX 関数がデータを実際に転送します。  クラス ライブラリには、一般的なすべてのデータ型に対する RFX 関数が用意されています。  RFX 関数の詳細については、「[レコード フィールド エクスチェンジ : RFX 関数の使い方](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)」を参照してください。  
  
    > [!NOTE]
    >  結果セット内の列の順序と `DoFieldExchange` での RFX 関数呼び出しの順序は、一致させる必要があります。  
  
-   フレームワークは、関数 `DoFieldExchange` を呼び出すときに、[CFieldExchange](../../mfc/reference/cfieldexchange-class.md) オブジェクトへのポインター `pFX` を渡します。  この `CFieldExchange` オブジェクトは、`DoFieldExchange` で実行する操作、データの転送方向などのコンテキスト情報を指定します。  
  
##  <a name="_core_the_recordset_constructor"></a> レコードセット コンストラクター  
 ウィザードが生成するレコードセットのコンストラクターには、RFX に関連する次の 2 つの処理があります。  
  
-   各フィールド データ メンバーの初期化  
  
-   データ メンバー [m\_nFields](../Topic/CRecordset::m_nFields.md) の初期化。このメンバー変数にはフィールド データ メンバー変数の数が格納されます。  
  
 `CSections` レコードセットのコンストラクターは、次のようになります。  
  
```  
CSections::CSections(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
   m_strCourseID = "";  
   m_strInstructorID = "";  
   m_strRoomNo = "";  
   m_strSchedule = "";  
   m_strSectionNo = "";  
   m_nFields = 5;  
}  
```  
  
> [!NOTE]
>  フィールド データ メンバーを手動で追加する場合は、新しい列を動的にバインドする場合と同様に、`m_nFields` の値を増加させる必要があります。  たとえば、次のようなコード行を追加します。  
  
```  
m_nFields += 3;  
```  
  
 このコードは、新しいフィールドを 3 つ追加します。  パラメーター データ メンバーを追加する場合は、パラメーター データ メンバーの数が格納される [m\_nParams](../Topic/CRecordset::m_nParams.md) データ メンバーを初期化する必要があります。  `m_nParams` の初期化コードも、かっこの外に書きます。  
  
## 参照  
 [レコード フィールド エクスチェンジ \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)