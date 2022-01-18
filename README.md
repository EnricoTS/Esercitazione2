# Esercitazione2

class ExamException(Exception):
      pass


class MovingAverage():
      def __init__(self, n):
            self.n = n
            if n <= 0:
                  raise ExamException('La finestra non puo essere 0 o meno')
            if not isinstance(n, int):
                  raise ExamException('La finestra deve essere di tipo int')
            

      def compute(self,lista):
            if len(lista) <= 0:
                  raise ExamException('La lista e vuota')
            if not isinstance(self.n, int):
                  raise ExamException('La finestra deve essere di tipo int')
            if len(lista) < self.n:
                  raise ExamException('Elementi di lista in meno della lunghezza della finestra')

            
                  
            ans = []
            for i in range(len(lista)-self.n+1):
                  try:
                        media = sum(lista[i:(self.n)+i])/self.n
                  except TypeError :
                        raise ExamException('Trovato elemento che non appartiene agli integer')
                  ans.append(media)
            return ans
                   



##moving_average = MovingAverage(-1)
##result = moving_average.compute([2,4,8,16])
##print(result)
##            
