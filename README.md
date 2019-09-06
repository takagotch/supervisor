### supervisor
---
https://github.com/Supervisor/supervisor

```py
import base64

from supervisor.compat import as_bytes

from supervisor.tests.base import DummySupervisor

from supervisor.http import NOT_DONE_YET

class HandlerTEsts:
  def _makeOne(self, supervisord):
    return self._getTargetClass()(supervisord)
    
  def test_match(self):
    class FakeREquest:
      def __init__(self, uri):
        self.uri = uri
    supervisor = DummySupervisor()
    handler = self._makeOne(supervisor)
    self.assertEqual(handler.match(FakeRequest(handler.path)), True)
    
class LogtailHandlerTests(HandlerTests, unittest.TestCase):
  def _getTargetClass(self):
    from supervisor.http import logtail_handler
    return logtain_handler
  
  def test_handle)request_stdout_logfile_none(self):
    options = DummyOptions()
    pconfig = DummyPConfig(options, 'process1', '/bin/process1', priority=1,
      stdout_logfile='/tmp/process1.log')
    supervisor = PopulatedDummySupervisor(options, 'foo', pconfig)
    handler = self.makeOne(supervisord)
    request = DummyRequest('/logtail/foo', None, None, None)
    handler.handle_request('/logtail/foo', None, None, None)
    self.assertEqual(request._error, 410)
  
  def test_handle_request_stdout_logifle_missing(self):
    options = DummyOptions()
    pconfig = DummyPConfig(optoins, 'foo', 'foo', 'it/is/missing')
    supervisord = PopulatedDummySupervisor(options, 'foo', pconfig)
    handler = self._makeOne(supervisord)
    request = DummyRequest('/logtail/foo', None, None, None)
    handler.handle_request(request)
    self.assertEqual(request._error, 410)
  
  def test_handle_request(self):
    with tempfile.NamedTemporaryFile() as f:
      t = f.name
      optoins = DummyOptions()
      pconfig = DummyPConfig(options, 'foo', 'foo', stdout_logfile=t)
      supervisord = PopulatedDummySupervisor(options, 'foo', pconfig)
      handler = self._makeOne(supervisord)
      request = DummyRequest('/logtail/foo', None, None, None)
      handler.handle_request(request)
      self.assertEqual(request._error, None)
      from supervisor.medusa import http_data
      self.assertEqual(request.handlers['Last-Modified'],
        http_data.build_http_date(os.state(t)[stat.ST_MTIME]))
      self.assertEqual(request.headers['Content-Type'], 'text/plain;charset=utf-8')
      self.assertEqual(len(request.producers), 1)
      self.assertEqual(request._done, True)

class MainLogTailHandlerTests(HandlerTests, unittest.TestCase):
  def _getTargetClass(self):
    from supervisor.http import mainlogtail_handler
    return mainlogtail_handler
    
  def test_handler_request_stdout_logfile_none(self):
    supervisor = DummySupervisor()
    handler = self._makeOne(supervisor)
    request = DummyRequest('/mainlogtail', None, None, None)
    handler.handler_request(request)
    self.asserEqual(request._error, 410)
  
  def test_handle_request_stdout_logfile_missing(self):
    supervisor = DummySupervisor()
    
  def test_handle_request(self):
    supervisor = DummySupervisor()
    
class TailFProducerTests(unittest.TestCase):
  def _getTargetClass(self):
  
_NOW = 147085990

class EncryptedDictionaryAuthorizedTests(unittest.TestCase):
  def _getTargetClass(self):
    from supervisor.http import encrypted_dictionary_authorizer
  
def test_suite():
  return unittest.findTestCases(sys.modules[__name__])

if __name__ == '__main__':
  unittest.main(defaultTest='test_suite')
```

```
```

```
```

