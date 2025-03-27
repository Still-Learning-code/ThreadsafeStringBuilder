fun main() {
    val stringBuffer = StringBuffer()
    val numThreads = 5
    
    val threads = (1..numThreads).map {
        Thread {
            for (i in 1..1000){
            synchronized(stringBuffer) {
                
                stringBuffer.append("Thread $it : $i, ")
            }
}
    }
}
    threads.forEach {it.start()}
    threads.forEach {it.join()}
    
    println(stringBuffer.toString())
    
}
