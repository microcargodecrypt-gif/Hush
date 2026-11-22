# Third-party notices

`Hush.html` bundles the open-source libraries below so that it can run offline. Each one stays under its own licence. Their original copyright and licence comments are kept inside the HTML file, next to the code they cover.

Hush's own code is under the Apache License 2.0 (see [LICENSE](LICENSE) and [NOTICE](NOTICE)). All bundled licences are permissive and compatible with it.

| Library | Version | Used for | Licence | Source |
| --- | --- | --- | --- | --- |
| SheetJS Community Edition (xlsx.js), including its codepage and CRC-32 modules | 0.18.5 | Reading and writing Excel and CSV files | Apache-2.0 | https://git.sheetjs.com/sheetjs/sheetjs |
| PDF.js and its worker (Mozilla) | 3.11.174 | Reading text from PDF files | Apache-2.0 | https://github.com/mozilla/pdf.js |
| jsPDF | 2.5.1 | Writing PDF files | MIT | https://github.com/parallax/jsPDF |
| JSZip | 3.10.1 | Reading and writing .docx files and building the .zip download | MIT or GPLv3, used here under MIT | https://github.com/Stuk/jszip |
| pako (inside JSZip) | as bundled by JSZip 3.10.1 | Compression | MIT, with parts under the zlib licence | https://github.com/nodeca/pako |

## Apache-2.0 libraries

### SheetJS Community Edition

Copyright (C) 2012-present SheetJS LLC

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0, and the same text is in this repository's [LICENSE](LICENSE) file.

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

### PDF.js

Copyright 2023 Mozilla Foundation

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0, and the same text is in this repository's [LICENSE](LICENSE) file.

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

The bundled PDF.js files are unmodified builds.

## MIT libraries

### jsPDF

Copyright (c) 2010-2021 James Hall, https://github.com/MrRio/jsPDF
2015-2021 yWorks GmbH, http://www.yworks.com
and the other contributors listed in the licence comment at the top of the jsPDF section of `Hush.html`.

jsPDF's distributed build also contains small components by other authors (for example a colour parser by Stoyan Stefanov, an MD5 routine by Joseph Myers, an RC4 routine from FPDF, the omggif GIF codec and a WebP decoder). jsPDF ships them as part of its MIT-licensed build, and their original notes are kept in the file.

### JSZip

Copyright (c) 2009-2016 Stuart Knightley, David Duponchel, Franz Buchinger, António Afonso

JSZip is dual-licensed under the MIT license or GPLv3. This project uses it under the MIT license.

### pako

Copyright (C) 2014-2017 by Vitaly Puzrin and Andrei Tupitcin

pako is released under the MIT license. Some parts are ported from zlib, (C) 1995-2013 Jean-loup Gailly and Mark Adler, under the zlib licence.

### MIT License text (applies to jsPDF, JSZip and pako, with the copyright lines above)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

### zlib licence (applies to the zlib-derived parts of pako)

This software is provided 'as-is', without any express or implied warranty. In no event will the authors be held liable for any damages arising from the use of this software.

Permission is granted to anyone to use this software for any purpose, including commercial applications, and to alter it and redistribute it freely, subject to the following restrictions:

1. The origin of this software must not be misrepresented; you must not claim that you wrote the original software. If you use this software in a product, an acknowledgment in the product documentation would be appreciated but is not required.
2. Altered source versions must be plainly marked as such, and must not be misrepresented as being the original software.
3. This notice may not be removed or altered from any source distribution.

## Updating a library

When you upgrade or add a bundled library, update the table above, keep its licence comment in the HTML file, and check that its licence is compatible with Apache-2.0.
