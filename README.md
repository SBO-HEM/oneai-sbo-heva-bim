# oneai-sbo-heva-bim Test
#setwd("/home/oneai/sbo-heva-bimmm")
#install.packages("shiny", dependencies = TRUE)
library(shiny)

ui <- fluidPage(
  titlePanel("Hello Shiny"),
  
  sidebarLayout(
    sidebarPanel(
      textInput("name", "Enter your name:", "Ajay")
    ),
    
    mainPanel(
      h3("Output:"),
      textOutput("greeting")
    )
  )
)

server <- function(input, output) {
  output$greeting <- renderText({
    paste("Hello", input$name)
  })
}

shinyApp(ui = ui, server = server)
Budget Impact Model in R Shiny
