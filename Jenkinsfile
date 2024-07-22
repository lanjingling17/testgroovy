// def ansiToHtml = { text ->
//     def ansiEscape = [
//         '\033[0m'  : '</span>',  // Reset
//         '\033[1m'  : '<span style="font-weight:bold">',  // Bold
//         '\033[3m'  : '<span style="font-style:italic">',  // Italic
//         '\033[4m'  : '<span style="text-decoration:underline">',  // Underline
//         '\033[30m' : '<span style="color:black">',  // Black
//         '\033[31m' : '<span style="color:red">',  // Red
//         '\033[32m' : '<span style="color:green">',  // Green
//         '\033[33m' : '<span style="color:yellow">',  // Yellow
//         '\033[34m' : '<span style="color:blue">',  // Blue
//         '\033[35m' : '<span style="color:magenta">',  // Magenta
//         '\033[36m' : '<span style="color:cyan">',  // Cyan
//         '\033[37m' : '<span style="color:white">',  // White
//         '\033[92m' : '<span style="color:cyan">',  // Light Cyan
//     ]

//     def ansiPattern = ~/\033\[\d+m/
//     def htmlText = text.replaceAll(ansiPattern) { match ->
//         ansiEscape.get(match, '')
//     }

//     return htmlText
// }
// // 进行转换操作
// def htmlFilePath = "output_parallel/report.html"
// // def file = new File(htmlFilePath)
// // def content = file.getText('UTF-8')

// // def html_content = ansiToHtml(content)
// // file.setText(html_content, 'UTF-8')
// // 读取文件内容
// def content = readFile(file: htmlFilePath)

// // 修改HTML内容（如果需要的话）
// def htmlContent = ansiToHtml(content)

// // 写入修改后的HTML内容
// writeFile(file: htmlFilePath, text: htmlContent)
pipeline {
    agent any

    stages {
        stage('Convert Report') {
            steps {
                script {
                    // 进入指定目录
                    dir("genesis-pm-api-tests") {
                        // ANSI 转换函数
                        def ansiToHtml = { text ->
                            def ansiEscape = [
                                '\033[0m'  : '</span>',  // Reset
                                '\033[1m'  : '<span style="font-weight:bold">',  // Bold
                                '\033[3m'  : '<span style="font-style:italic">',  // Italic
                                '\033[4m'  : '<span style="text-decoration:underline">',  // Underline
                                '\033[30m' : '<span style="color:black">',  // Black
                                '\033[31m' : '<span style="color:red">',  // Red
                                '\033[32m' : '<span style="color:green">',  // Green
                                '\033[33m' : '<span style="color:yellow">',  // Yellow
                                '\033[34m' : '<span style="color:blue">',  // Blue
                                '\033[35m' : '<span style="color:magenta">',  // Magenta
                                '\033[36m' : '<span style="color:cyan">',  // Cyan
                                '\033[37m' : '<span style="color:white">',  // White
                                '\033[92m' : '<span style="color:cyan">',  // Light Cyan
                            ]

                            def ansiPattern = ~/\033\[\d+m/
                            def htmlText = text.replaceAll(ansiPattern) { match ->
                                ansiEscape.get(match, '')
                            }

                            return htmlText
                        }


                        // // 定义 HTML 文件路径
                        // def htmlFilePath = "output_parallel/report.html"

                        // // 使用 Jenkins 的 readFile 读取文件内容
                        // def content = readFile(file: htmlFilePath)

                        

                        // // 调用 ansiToHtml 转换内容
                        // def htmlContent = ansiToHtml(content)

                        // // 写入转换后的 HTML 文件（如果需要）
                        // writeFile(file: htmlFilePath, text: htmlContent)




                        // 进行转换操作
                        def htmlFilePath = "output_parallel/report.html"
                        def file = new File(htmlFilePath)
                        def content = file.getText('UTF-8')

                        def html_content = ansiToHtml(content)
                        file.setText(html_content, 'UTF-8')
                    }
                }
            }
        }
    }
}