pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'python -V'
            }
        }
        stage('Test') {
            steps {
                script {
                    def code = """
def factorial(n):
  \"\"\"
  Функція для обчислення факторіала числа.

  Args:
    n: Ціле число.

  Returns:
    Факторіал числа n.
  \"\"\"

  if n < 0:
    raise ValueError(\"n має бути невід'ємним\")

  if n == 0:
    return 1

  else:
    return n * factorial(n-1)


def main():
  \"\"\"
  Функція для демонстрації роботи factorial().
  \"\"\"

  number = {number}
  result = factorial(number)
  print(f\"Факторіал числа {number} дорівнює {result}\")


if __name__ == \"__main__\":
  main()
"""
                    writeFile file: 'factorial.py', text: code
                    sh 'python factorial.py'
                }
            }
        }
    }
}
