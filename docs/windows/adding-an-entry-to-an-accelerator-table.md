---
title: "アクセラレータ テーブルへのエントリの追加 | Microsoft Docs"
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
  - "アクセラレータ テーブル [C++] エントリを追加します。"
  - "[新しいアクセラレータ] コマンド"
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# アクセラレータ テーブルへのエントリの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### <a name="to-add-an-entry-to-an-accelerator-table"></a>アクセラレータ テーブルにエントリを追加するには  
  
1.  アクセラレータ テーブルを開くことでそのアイコンをダブルクリックして [リソース ビュー](../windows/resource-view-window.md)します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  アクセラレータ テーブル内で右クリックし [ **新しいアクセラレータ** からショートカット メニューのまたはテーブルの下部にある空の行エントリをクリックします。  
  
3.  選択、 [ID](Id%20Property.xml) で新しい ID を入力 ID のドロップ ダウン リストから、または、 **ID** ボックス。  
  
4.  型、 [キー](../Topic/Accelerator%20Key%20Property.md) アクセラレータまたは右クリックとして使用する **キー タイピング** キーの組み合わせを設定するショートカット メニューから (、 **キー タイピング** コマンドが表示されます、 **編集** メニュー)。  
  
5.  変更、 [修飾子](../windows/accelerator-modifier-property.md) と [型](../windows/accelerator-type-property.md), 必要に応じて、します。  
  
6.  キーを押して **ENTER**します。  
  
    > [!NOTE]
    >  定義するすべてのアクセラレータが一意であることを確認します。 いくつかのキーの組み合わせを、同じ ID に問題なく割り当てることができます。たとえば、Ctrl + P と F8 は、どちらも ID_PRINT に割り当てることができます。 ただし、キーの組み合わせを複数の ID に割り当てると、うまく機能しません。たとえば、Ctrl + Z を ID_SPELL_CHECK と ID_THESAURUS の両方に割り当てる場合などです。  
  
 マネージ プロジェクトにリソースを追加する方法については、『 [.NET Framework 開発者ガイド](../Topic/Resources%20in%20Desktop%20Apps.md) 』の「 *アプリケーションのリソース* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [Walkthrough: Using Resources for Localization with ASPします。NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)します。  
  
 **Requirements**  
  
 Win32  
  
## <a name="see-also"></a>「  
 [アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)   
 [アクセラレータ エディター](../Topic/Accelerator%20Editor.md)