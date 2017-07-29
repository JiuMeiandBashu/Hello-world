# Hello-world
<?php
/**
 * 认证控制器
 * @author LWD
 * @category wkrj
 * @package Wkrj\Controller
 * @version 1.0
 */
namespace Wkrj\Controller;
use Think\Controller;
class AuthController extends Controller {
	//权限
	//public funcation _initialize(){
	//       if(session ('userName')==''){
	//       $this->redirect("/");
	//       }
	//
	//
	//
	//}
	public function _initialize(){//return;
		if (session('userName')=='') {
			$this->redirect("/");
		}
		if (session("rolerId")=='1'){
			return;
		}
		$group=strtolower(MODULE_NAME);
		$controller=strtolower(CONTROLLER_NAME);
		$action=strtolower(ACTION_NAME);
		$rule=strtolower($group.'/'.$controller.'/'.$action);
		if ($controller=='index'){
			return;
		}
    ?>
