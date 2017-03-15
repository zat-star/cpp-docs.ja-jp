---
title: "MFC ActiveX コントロール : シリアル化 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_wVerMinor"
  - "DoPropExchange"
  - "_wVerMajor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoPropExchange メソッド"
  - "ExchangeVersion メソッド"
  - "GetVersion メソッド"
  - "MFC ActiveX コントロール, シリアル化"
  - "MFC ActiveX コントロール, バージョン サポート"
  - "バージョン管理 (ActiveX コントロールの)"
  - "wVerMajor グローバル定数"
  - "wVerMinor グローバル定数"
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC ActiveX コントロール : シリアル化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ActiveX コントロールをシリアル化する方法について説明します。  シリアル化は、ディスク ファイルのような永続ストレージ メディアのへの読み取りおよび書き込みのプロセスです。  Microsoft Foundation Class \(MFC\) ライブラリはクラス `CObject`のシリアル化の組み込みサポートを提供します。  `COleControl` は 所持品の交換機構を使用して、ActiveX コントロールにこのサポートを拡張します。  
  
 ActiveX コントロールのシリアル化は、オーバーライドの [COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)によって実装されます。  Control オブジェクトの読み込みと保存の中に呼び出されたこの関数は変更通知のメンバー変数またはメンバー変数と実装されるすべてのプロパティを保存します。  
  
 次のトピックでは、ActiveX コントロールのシリアル化の主要な問題について説明します。:  
  
-   `DoPropExchange`関数のコントロール オブジェクトをシリアル化するために実装  
  
-   [シリアル化プロセスのカスタマイズ](#_core_customizing_the_default_behavior_of_dopropexchange)  
  
-   [バージョン サポートの実装](#_core_implementing_version_support)  
  
##  <a name="_core_implementing_the_dopropexchange_function"></a> DoPropExchange 関数の実装  
 コントロール プロジェクトを生成するには、ActiveX コントロール ウィザードを使用すると、複数の既定のハンドラー関数は [COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)の既定の実装を含む、コントロール クラスに自動的に追加されます。  次の例では、ActiveX コントロール ウィザードで生成されたクラスに追加するコード例を次に示します。:  
  
 [!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_1.cpp)]  
  
 プロパティを永続的にする場合は、所持品 swap 関数への呼び出しを追加して、`DoPropExchange` を変更します。  次の例では CircleShape のプロパティに **TRUE**の既定値がある CircleShape Boolean プロパティのカスタムのシリアル化を示します。、:  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_3.cpp)]  
  
 次の表は、コントロールのプロパティをシリアル化するために使用できる有効な所持品の swap 関数の一覧です:  
  
|所持品の swap 関数|目的|  
|------------------|--------|  
|**PX\_Blob \(\)**|型のバイナリ ラージ オブジェクト \(BLOB \(BLOB\) データ プロパティをシリアル化します。|  
|**PX\_Bool \(\)**|型のブール型プロパティをシリアル化します。|  
|**PX\_Color \(\)**|型のカラー プロパティをシリアル化します。|  
|**PX\_Currency \(\)**|型の **CY** \(通貨\) のプロパティをシリアル化します。|  
|**PX\_Double \(\)**|型の **double** のプロパティをシリアル化します。|  
|**PX\_Font \(\)**|フォントの種類のプロパティをシリアル化します。|  
|**PX\_Float \(\)**|型の **float** のプロパティをシリアル化します。|  
|**PX\_IUnknown \(\)**|型の `LPUNKNOWN`プロパティをシリアル化します。|  
|**PX\_Long \(\)**|型の **long** のプロパティをシリアル化します。|  
|**PX\_Picture \(\)**|型のピクチャ プロパティをシリアル化します。|  
|**PX\_Short \(\)**|型の **short** のプロパティをシリアル化します。|  
|**PX\_String \(\)**|型の `CString` のプロパティをシリアル化します。|  
|**PX\_ULong \(\)**|型の **ULONG** のプロパティをシリアル化します。|  
|**PX\_UShort \(\)**|型の **USHORT** のプロパティをシリアル化します。|  
  
 これらの詳細については所持品の交換機能し、" *MFC リファレンス"の*" [OLE コントロールの永続化](../mfc/reference/persistence-of-ole-controls.md) を参照します。  
  
##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> DoPropExchange の既定の動作のカスタマイズ  
 **DoPropertyExchange** の既定の実装では、基本クラス `COleControl` \(前のトピックで説明されているように\) を呼び出します。  これは自動的に `COleControl`でサポートされる使用するプロパティのセットをシリアル化してコントロールのカスタム プロパティをシリアル化するよりも多少の記憶領域が。  この呼び出しを削除すると、オブジェクトが重要検討したプロパティのみシリアル化できるようになります。  明示的にこれらの **PX\_** の呼び出しを追加するコントロール オブジェクトを保存したり、読み込むときにコントロールがシリアル化されない実装したかを知るストック プロパティが表示されます。  
  
##  <a name="_core_implementing_version_support"></a> バージョン サポートの実装  
 バージョンのサポートは変更された ActiveX コントロールが新しく永続的なプロパティを追加できます。また、コントロールの旧バージョンで作成された永続的な状態を検出し、読み込めます。  コントロールのバージョンを永続データの一部として使用できるようにするには、コントロールの `DoPropExchange` 関数の [COleControl::ExchangeVersion](../Topic/COleControl::ExchangeVersion.md) を呼び出します。  この呼び出しが自動的に ActiveX コントロールが ActiveX コントロール ウィザードを使用して作成された挿入されます。  これは、バージョンのサポートが必要である削除できます。  ただし、コントロールのサイズのコストはバージョン サポートが提供する追加された柔軟性に非常に小さい \(4 バイト\)。  
  
 コントロールが ActiveX コントロール ウィザードで作成されていない場合、`DoPropExchange` 関数の先頭に次の行を挿入することで、`COleControl::ExchangeVersion` の呼び出しを追加します。`COleControl::DoPropExchange`の呼び出しの前に\) :  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_4.cpp)]  
  
 バージョン番号として `DWORD` を使用できます。  既定として ActiveX コントロール ウィザードを使用 **\_wVerMinor** と **\_wVerMajor** で生成されたプロジェクト。  これらはプロジェクトの ActiveX コントロール クラスの実装ファイルで定義されているグローバル定数です。  `DoPropExchange` 関数の残りの中で、保存または取得しているバージョンを取得するに [CPropExchange::GetVersion](../Topic/CPropExchange::GetVersion.md) をいつでも呼び出すことができます。  
  
 次の例では、このサンプル コントロールのバージョン 1 に「ReleaseDate」プロパティだけです。  バージョン 2 「OriginalDate」プロパティを追加します。  コントロールが古いバージョンの永続的な状態を読み込むようにように指示する既定値に新しいプロパティのメンバー変数を初期化します。  
  
 [!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_5.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_4.cpp)]  
  
 既定では最新の形式は、古いデータ コントロールを「変換」します。  たとえば、コントロールのバージョン 2 バージョン 1 で格納されているデータを読み込めば、再度保存時バージョン 2 形式を記述します。  最後に、コントロールにデータを格納する場合は `ExchangeVersion`を呼び出す場合は、3 番目のパラメーターとして **FALSE** を渡します。  3 番目のパラメーターは省略可能に既定で **TRUE** です。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)