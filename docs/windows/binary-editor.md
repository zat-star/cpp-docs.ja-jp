---
title: "バイナリ エディター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.binary.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, Binary
- resources [Visual Studio], editing
- resource editors, Binary editor
- Binary editor
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4dade674fb32615e23904e6dbaf03d6c6ee0a371
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="binary-editor"></a>バイナリ エディター
> [!WARNING]
>  バイナリ エディターは Express Edition では使用できません。  
  
 バイナリ エディターを使うと、16 進形式または ASCII 形式を使用してバイナリ レベルでリソースを編集できます。 また、 [[検索] コマンド](/visualstudio/ide/reference/find-command) を使うと、ASCII 文字列や 16 進表現のバイト列を検索できます。 バイナリ エディターは、カスタム リソースや Visual Studio 環境でサポートされていない種類のリソースを表示したり、部分的に変更したりするときにだけ使うようにしてください。  
  
 バイナリ エディターを開くには、まず選択**ファイル &#124;です。新しい &#124;です。ファイル**、メイン メニューから、ファイルを選択し、編集、横にドロップダウン矢印をクリックする、**開く**ボタンをクリックし、選択**ファイルを開く (&) #124 です。バイナリ エディター**です。  
  
> [!CAUTION]
>  ダイアログ ボックス、イメージ、メニューなどのリソースをバイナリ エディターで編集することは危険です。 編集方法が正しくないと、リソースを破損し、本来のエディターで読み取ることができなくなる場合があります。  
  
> [!TIP]
>  バイナリ エディターをさまざまな状況で使用している場合、マウスの右ボタンをクリックするとリソースに対応したショートカット メニューを表示できます。 使用できるコマンドは、ポインターの位置によって異なります。 たとえば、16 進の値が選ばれているバイナリ エディターをポイントした状態でクリックすると、ショートカット メニューには **[切り取り]**、 **[コピー]**、 **[貼り付け]** の各コマンドが表示されます。  
  
 バイナリ エディターでは、次の作業ができます。  
  
-   [バイナリ編集するリソースを開く](../windows/opening-a-resource-for-binary-editing.md)  
  
-   [バイナリ データを編集する](../windows/editing-binary-data.md)  
  
-   [バイナリ データを検索する](../windows/finding-binary-data.md)  
  
-   [新しいカスタム リソースまたはデータ リソースを作成する](../windows/creating-a-new-custom-or-data-resource.md)  
  
## <a name="managed-resources"></a>マネージ リソース  
 [イメージ エディター](../windows/image-editor-for-icons.md) とバイナリ エディターを使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
### <a name="requirements"></a>必要条件  
 なし  
  
## <a name="see-also"></a>参照  
 [リソース エディター](../windows/resource-editors.md)

