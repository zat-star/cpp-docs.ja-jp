---
title: "方法: メニュー、サブメニュー、ショートカット メニューの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "コマンド バー、アーキテクチャ"
  - "メニュー、作成"
  - "メニュー、アーキテクチャ"
  - "コマンド、メニュー"
  - "メニュー"
ms.assetid: 62004fd9-7f99-4f00-8d01-1dde53e23dbb
caps.latest.revision: 46
caps.handback.revision: 46
manager: "douge"
---
# 方法: メニュー、サブメニュー、ショートカット メニューの作成
Visual Studio 統合開発環境 \(IDE\) にメニューを追加する場合、VSPackage では、コマンド グループ メニューの [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)] アーキテクチャを使用する必要があります。 コマンド グループ メニューを使用すると、コンポーネントと IDE でコマンドを共有できます。 コマンド グループ メニューの詳細については、「[Vspackage でのユーザー インターフェイス要素を追加する方法](../Topic/How%20VSPackages%20Add%20User%20Interface%20Elements.md)」をご覧ください。  
  
 Vspackage では、メニューは .vsct ファイルの [Menus](../Topic/Menus%20Element.md) セクションで定義されています。 .vsct ファイルは、メニュー、ツール バー、グループ、コマンドを定義します。 コマンドは、機能を実行するためにユーザーがクリックするものです。 グループは、コマンドのコンテナーです。 メニューは、グループのコンテナーです。 基本的なメニューを作成するには、メニュー、コマンド グループ、および少なくとも 1 つのコマンドを作成する必要があります。  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] でメニューが表示される基本的な方法は、次の 3 つです。  
  
-   メイン メニュー バーのメニューとして。  
  
-   別のメニューのサブメニューとして。  
  
-   ショートカット メニューとして \(通常、右クリックして表示\)。  
  
 このトピックでは、それぞれの種類のメニューを作成する方法を説明します。 また、このチュートリアルでは、次の方法も示します。  
  
-   [Visual Studio のメニュー バーにメニューを追加します。](../Topic/Adding%20a%20Menu%20to%20the%20Visual%20Studio%20Menu%20Bar.md)  
  
-   [メニューのサブメニューの追加](../Topic/Adding%20a%20Submenu%20to%20a%20Menu.md)  
  
-   [ツール ウィンドウのショートカット メニューを追加します。](../Topic/Adding%20a%20Shortcut%20Menu%20in%20a%20Tool%20Window.md)  
  
### メニュー、サブメニュー、ショートカット メニューを作成するには  
  
1.  プロジェクトで .vsct ファイルをダブルクリックして、エディターで開きます。  
  
     プロジェクトに .vsct ファイルがない場合は、追加します。 Visual Studio のパッケージ テンプレートを使用してパッケージを作成する場合は、**メニュー コマンド**を選択します。この操作で .vsct ファイルが生成されます。  
  
2.  `Symbols` セクションで、グループとコマンドを含んでいる [GuidSymbol](../Topic/GuidSymbol%20Element.md) 要素を見つけます。  
  
3.  次の例に示すように、追加するメニュー、グループ、コマンドごとに [IDSymbol](../Topic/IDSymbol%20Element.md) 要素を作成します。  
  
     [!CODE [ButtonGroup#01](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#01)]  
  
     `GuidSymbol` 要素と `IDSymbol` 要素の `name` 属性は、新規のメニュー、グループ、コマンドそれぞれの GUID:ID ペアを提供します。`GUID` は、VSPackage に定義されているコマンド セットを表します。 複数のコマンド セットを定義できます。 GUID:ID ペアは、それぞれ一意である必要があります。  
  
4.  次のようにして、`Menus` セクションに新しいメニューを定義します。  
  
    1.  新しいメニューの GUID:ID が一致するように `guid` フィールドと `id` フィールドを設定します。  
  
    2.  `priority` 属性を設定します。  
  
         `priority` 属性は、メニューの場所を親グループ内の他のオブジェクトの中で特定するために .vsct ファイルで使用されます。  
  
         優先順位値が低いメニューは、優先順位値の高いメニューの前に表示されます。 優先順位値の重複は許容されますが、優先順位が同じメニューの相対的な位置は実行時に VSPackage が処理される順序によって決まり、その順序を事前に設定することはできません。`priority` 属性を省略すると、その値は 0 に設定されます。  
  
         ショートカット メニューの配置は呼び出し元のコードによって決まるので、ショートカット メニューには優先順位を設定しないでください。  
  
    3.  メニューおよびサブメニューの場合は、`type` 属性を `Menu` に設定します。これに一般的なメニューが記述されます。 ショートカット メニューの場合は、`type` 属性を `Context` に設定します。  
  
         ツール バーやメニュー コントローラーなど、使用できる他の種類のメニューに関する詳細は、「[Menu 要素](../Topic/Menu%20Element.md)」をご覧ください。  
  
    4.  メニューの定義で、[Strings](../Topic/Strings%20Element.md) セクションを作成します。このセクションには、IDE に表示されるメニューの名前を格納する [ButtonText](../Topic/ButtonText%20Element.md) 要素と、**\[コマンド\]** ウィンドウのメニューにアクセスする際に使用されるコマンドの名前を格納する [CommandName](../Topic/CommandName%20Element.md) 要素が含まれます。  
  
         ボタンの文字列に '&' 文字を含めると、Alt キーと '&' の直後に続く文字とを押すことで、メニューを開くことができるようになります。  
  
    5.  必要に応じて、コマンド フラグを追加し、メニューの外観と動作を変更します。 これを行うには、メニュー定義に [CommandFlag](../Topic/Command%20Flag%20Element.md) 要素を追加します。 詳細については、「[コマンドのフラグ要素](../Topic/Command%20Flag%20Element.md)」を参照してください。  
  
5.  このメニューの親を設定します。 標準メニューやサブメニューの場合は、設計に応じて次のいずれかの方法でこれを行うことができます。  
  
    -   `Menu` 要素に [Parent](../Topic/Parent%20Element.md) 要素を作成し、その要素の `guid` フィールドと `id` フィールドを、メニューをホストするグループ \(*プライマリ親グループ*とも呼ばれます\) の GUID:ID に設定します。 親グループは、`Symbols` セクションで作成したグループ、別のパッケージからのグループ、IDE からのグループのいずれかになります。 たとえば、メニューを IDE のトップ レベル メニュー バーの **\[ツール\]** メニューの近くに追加するには、親を guidSHLMainMenu:IDG\_VS\_MM\_TOOLSADDINS に設定します。  
  
         次の例では、Visual Studio のメニュー バーに表示されるメニューを示します。  
  
         [!CODE [TopLevelMenu#01](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#01)]  
  
    -   コマンド配置を使用してメニューを配置する場合には、`Parent` 要素を省略することもできます。 次の例に示すように、`Symbols` セクションの前に [CommandPlacements](../Topic/CommandPlacements%20Element.md) セクションを作成し、メニューの GUID:ID を持つ [CommandPlacement](../Topic/CommandPlacement%20Element.md) 要素、優先順位、親を追加します。  
  
         [!CODE [ButtonGroup#04](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#04)]  
  
         GUID:ID が同じで親が異なる複数のコマンド配置を作成すると、メニューが複数の場所に表示されます。 詳細については、「[CommandPlacements 要素](../Topic/CommandPlacements%20Element.md)」を参照してください。  
  
     標準メニューには、その親として、Visual Studio のメニュー バー上にグループを設定する必要があります。 サブメニューの場合、親は別のメニュー上 \(または、ツールバーか他の種類のメニュー上\) のグループである必要があります。 メニューまたはサブメニューを表示するには、アクティブなコマンドを少なくとも 1 つ含むグループをホスティングするか、`AlwaysCreate` コマンド フラグを設定する必要があります。  
  
     ショートカット メニューには、親またはコマンドの配置はありません。 代わりに、コードでアクティブ化される必要があります。 通常、コントロール サーフェイスで右クリックするとショートカット メニューがアクティブ化されます。 次の例では、ショートカット メニューを定義します。  
  
     [!CODE [ButtonGroup#06](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#06)]  
  
6.  [Groups](../Topic/Groups%20Element.md) セクションで、メニューに表示するコマンドを格納する [Group](../Topic/Group%20Element.md) 要素を作成します。`Symbols` セクションには、新しい `Group` 要素と同じ GUID:ID を持つエントリを含める必要があります。  
  
    1.  メニューの目的の場所に表示されるように、グループの優先順位を設定します。  
  
         メニューの各グループの境界は、水平線として表示されます。  
  
    2.  新しいグループの親を、作成したメニューの GUID:ID に設定します。 これにより、コマンドのグループがメニューに配置されます。  
  
     次の例のグループは、前の例で示したトップ レベル メニューに表示されます。  
  
     [!CODE [TopLevelMenu#02](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#02)]  
  
     メニューには、コマンドとサブメニューの両方を含めることができます。 サブメニュー \(カスケード メニューとも呼ばれます\) もメニューの 1 つですが、別のメニューのグループに追加されており、追加先のメニューが呼び出されたときにのみ呼び出されます。 次の例に示すメニューをトップ レベル メニューのグループ内に配置すると、このメニューはサブメニューになります。  
  
     [!CODE [TopLevelMenu#06](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#06)]  
  
7.  コマンドのエントリを [Buttons](../Topic/Buttons%20Element.md) セクションに作成し、それぞれのエントリの親をグループの GUID:ID に設定して、メニューにコマンドを追加します。 各 [Button](../Topic/Button%20Element.md) 要素には、`Symbols` セクションのエントリに対応する GUID:ID を設定する必要があります。  
  
     コマンドがグループ内で表示される順序を指定するには、各ボタン エントリの `priority` 属性を使用します。  
  
     次の例では、トップ レベル メニューに表示されるコマンドを定義します。  
  
     [!CODE [TopLevelMenu#03](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#03)]  
  
     ボタンおよびメニュー項目の詳細については、「[Button 要素](../Topic/Button%20Element.md)」をご覧ください。  
  
     コードにメニュー コマンドを実装する方法については、「[MenuCommand と  OleMenuCommand](../misc/menucommands-vs-olemenucommands.md)」か、このトピックで既に説明したチュートリアルをご覧ください。  
  
### ショートカット メニューをアクティブ化するには  
  
1.  ショートカット メニューの GUID:ID を取得します。 既定で、パッケージ テンプレートは PkgCmdID.cs ファイルに `GuidList` クラスを作成してコマンド セットの GUID を保持します。 また、このテンプレートは PkgCmdId.cs ファイルに `PkgCmdIdList` クラスも作成します。これにより、テンプレートで宣言されるコマンドの整数 ID 値が保持されます。 ショートカット メニューおよび追加のコマンドは、テンプレートが完了してから宣言する必要があります。 これらの宣言の例を次に示します。  
  
     [!code-cs[TWShortcutMenu#12](../misc/codesnippet/CSharp/how-to-create-menus-submenus-and-shortcut-menus_8.cs)]  
  
     GUID 値および ID 値を直接使用する場合は、この手順を省略できます。 ただし、読みやすくするためにここで値を設定することをお勧めします。  
  
2.  イベント ハンドラーにアタッチします。 通常、ショートカット メニューは、次の例で示すようにコントロール サーフェイスの右クリックにアタッチします。  
  
     [!code-cs[TWShortcutMenu#43](../misc/codesnippet/CSharp/how-to-create-menus-submenus-and-shortcut-menus_9.cs)]  
  
     <xref:System.Windows.Forms.Control.PointToScreen%2A> メソッドは、クリック位置 \(コントロールを基準とした相対位置\) を画面位置に変換します。<xref:Microsoft.VisualStudio.Shell.OleMenuCommandService.ShowContextMenu%2A> メソッドは、ショートカット メニューを表示します。  
  
     イベント ハンドラーを含むファイルには、<xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> クラスにアクセスするための <xref:System.ComponentModel.Design> 名前空間、および <xref:System.ComponentModel.Design.IMenuCommandService> インターフェイスにアクセスするための <xref:Microsoft.VisualStudio.Shell> 名前空間を含める必要があります。  
  
     [!code-cs[TWShortcutMenu#41](../misc/codesnippet/CSharp/how-to-create-menus-submenus-and-shortcut-menus_10.cs)]  
  
## 参照  
 [MenuCommand と  OleMenuCommand](../misc/menucommands-vs-olemenucommands.md)   
 [VSCT XML スキーマ リファレンス](../Topic/VSCT%20XML%20Schema%20Reference.md)   
 [拡張メニューとコマンド](../Topic/Extending%20Menus%20and%20Commands.md)