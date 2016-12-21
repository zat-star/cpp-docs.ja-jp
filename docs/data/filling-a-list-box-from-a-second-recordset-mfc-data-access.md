---
title: "セカンド レコードセットを利用してリスト ボックスを表示する方法 (MFC データ アクセス) | Microsoft Docs"
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
  - "CComboBox クラス, 格納 (セカンド行セットからオブジェクトに)"
  - "CListCtrl クラス, 格納 (セカンド レコードセットから)"
  - "コンボ ボックス [C++], 格納 (セカンド レコードセットから)"
  - "DAO レコードセット"
  - "DAO レコードセット, 格納 (リスト ボックスまたはコンボ ボックスに)"
  - "格納 (リストまたはコンボ ボックスに)"
  - "リスト ボックス, 格納 (セカンド レコードセットから)"
  - "複数のレコードセット (レコード ビューの)"
  - "ODBC レコードセット [C++], 格納 (リスト ボックスまたはコンボ ボックスに)"
  - "レコード ビュー, 格納 (リスト ボックスに)"
  - "レコードセット [C++], 格納 (リスト ボックスまたはコンボ ボックスに)"
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# セカンド レコードセットを利用してリスト ボックスを表示する方法 (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既定では、1 つのレコード ビューは 1 つのレコードセット オブジェクトに関連付けられ、そのオブジェクトのフィールドがレコード ビューのコントロールに対応付けられます。  場合によっては、レコード ビューにリスト ボックス コントロールまたはコンボ ボックス コントロールを配置して、そこに別の \(セカンド\) レコードセット オブジェクトの複数の値を設定することが必要となります。  ユーザーは、そのリスト ボックスを使用して、レコード ビューに表示された新しいカテゴリの情報を選択できます。  このトピックでは、いつどのようにこの処理を実行するかについて説明します。  
  
> [!TIP]
>  コンボ ボックスまたはリスト ボックスにデータ ソースから値を設定すると、処理が遅くなることがあります。  多数のレコードを含むレコードセットからコントロールに値を設定しようとする場合は、注意が必要です。  
  
 このトピックで使用するモデルは、フォームのコントロールに値を設定するメイン レコードセットと、リスト ボックスまたはコンボ ボックスに値を設定するセカンド レコードセットで構成されます。  リスト ボックスから文字列を選択すると、その文字列に基づいてメイン レコードセットのクエリが再実行されるようにプログラミングされています。  次の手順ではコンボ ボックスを使用しますが、リスト ボックスの場合も同様です。  
  
#### セカンド レコードセットからコンボ ボックスまたはリスト ボックスの値を設定するには  
  
1.  レコードセット オブジェクト \(ODBC の場合は [CRecordset](../Topic/CRecordset%20Class.md)、DAO の場合は [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)\) を作成します。  
  
2.  コンボ ボックス コントロールを表す [CComboBox](../mfc/reference/ccombobox-class.md) オブジェクトへのポインターを取得します。  
  
3.  コンボ ボックスの以前の内容をすべて空にします。  
  
4.  レコードセットのすべてのレコードについて、各レコードの文字列に対してそれぞれ [CComboBox::AddString](../Topic/CComboBox::AddString.md) を呼び出し、コンボ ボックスに追加します。  
  
5.  コンボ ボックスの選択内容を初期化します。  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
    // ...  
  
    // Fill the combo box with all of the courses  
    CENROLLDoc* pDoc = GetDocument();  
    if (!pDoc->m_courseSet.Open())  
        return;  
  
    // ...  
  
    m_ctlCourseList.ResetContent();  
    if (pDoc->m_courseSet.IsOpen())  
    {   
        while (!pDoc->m_courseSet.IsEOF() )  
        {  
            m_ctlCourseList.AddString(  
                pDoc->m_courseSet.m_CourseID);  
            pDoc->m_courseSet.MoveNext();  
        }  
    }  
    m_ctlCourseList.SetCurSel(0);  
}  
```  
  
 この関数では、提供されるコースごとに 1 つのレコードを含むセカンド レコードセット `m_courseSet` と、レコード ビュー クラスに格納された `CComboBox` コントロール `m_ctlCourseList` を使用しています。  
  
 この関数は、ドキュメントから `m_courseSet` を取得して開きます。  次に、`m_ctlCourseList` を空にして、`m_courseSet` を 1 レコードずつ処理します。  各レコードに対してコンボ ボックスの `AddString` メンバー関数が呼び出されて、レコードからコース ID 値が追加されます。  最後に、コンボ ボックスの選択内容が設定されます。  
  
## 参照  
 [レコード ビュー \(MFC データ アクセス\)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)