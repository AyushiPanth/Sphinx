===========
My Approach
===========

Print Board
===========



Valid Move
==========

.. code-block:: python

   def valid(piece: str, from: str, to: str):
      file1 = from[0].upper
      file2 = to[0].upper
      rank1 = int(from[1])
      rank2 = int(to[1])
      moved_by = (abs(ord(file1) - ord(file2)), abs(rank1) - rank2)

      def pawn():
         return moved_by[0] == 0

      def bishop():
         return moved_by[0] == moved_by[1]

      def knight():
         return moved_by in [(1,2), (2,1)]

      def rook():
         return moved_by[0] == 0 or moved_by[1] == 0

      return {"R": rook, "N": knight, "B": bishop, "P": pawn}[piece]()


