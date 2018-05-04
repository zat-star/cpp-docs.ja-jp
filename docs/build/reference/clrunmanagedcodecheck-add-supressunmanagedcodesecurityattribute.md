---
title: -CLRUNMANAGEDCODECHECK (Supressunmanagedcodesecurityattribute) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
dev_langs:
- C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a00563460519225b38b1c5e745679da943d890cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (SupressUnmanagedCodeSecurityAttribute の追加)
**/CLRUNMANAGEDCODECHECK**リンカーを適用するかどうかを指定<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>リンカーによって生成されたに`PInvoke`マネージ コードからネイティブ Dll への呼び出しです。  
  
## <a name="syntax"></a>構文  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 既定では、リンカーがリンカーによって生成されたに SuppressUnmanagedCodeSecurityAttribute を適用`PInvoke`呼び出しです。 ときに **/CLRUNMANAGEDCODECHECK**が有効になって、SuppressUnmanagedCodeSecurityAttribute が適用されません。  
  
 リンカーは、コンパイルされたオブジェクトに属性を追加するだけ **/clr**または **/clr: 純粋な**します。 ただし、 **/clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 では廃止し、コンパイラの将来のバージョンで削除される予定です。  
  
 A`PInvoke`呼び出しは、リンカーは、マネージ呼び出し元からの参照を満たすためにマネージ シンボルを検索することはできませんが、その参照を満たすためにネイティブ シンボルを検索することができる場合、リンカーによって生成されます。 詳細については`PInvoke`を参照してください[マネージ コードからネイティブ関数を呼び出して](../../dotnet/calling-native-functions-from-managed-code.md)です。  
  
 使用する場合は、 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 、コードでは明示的に設定する **/CLRUNMANAGEDCODECHECK**です。 イメージに、SuppressUnmanagedCodeSecurity と AllowPartiallyTrustedCallers 属性が含まれている場合は、潜在的なセキュリティの脆弱性を勧めします。  
  
 参照してください[安全なコーディングのガイドライン、アンマネージ コード](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code)SuppressUnmanagedCodeSecurityAttribute を使用する場合の詳細についてはします。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**詳細**プロパティ ページ。  
  
5.  変更、 **CLR アンマネージ コード チェック**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)